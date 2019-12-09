<template>
   <div>
       <h1>{{ title }}</h1>
       <select v-model="selected" name="book" v-on:change="GetText($event)">
           <option v-for="book in books" v-bind:key="book.id" v-bind:value="book.url">{{ book.name }} </option>
       </select>
       <span>Selected: {{ selected }}</span>
       <div id="content">{{ contents }}</div>
   </div> 
</template>
<script>
export default {
   name: 'EViewer',
   props: {
   },
   data: function(){
       return {
           title: 'No Document',
           content: 'No Contents',
           selected: '',
           books:[
                {id: '1', name: '羅生門', url: 'https://www.aozora.gr.jp/cards/000879/files/127_15260.html'},
                {id: '2', name: 'こころ', url: 'https://www.aozora.gr.jp/cards/000879/files/127_15260.html'},
                {id: '3', name: '銀河鉄道の夜', url: 'https://www.aozora.gr.jp/cards/000879/files/127_15260.html'},
                {id: '4', name: 'The Old Man And The Sea', url: 'https://www.aozora.gr.jp/cards/000879/files/127_15260.html'},
                {id: '5', name: 'Huckleberry Finn', url: 'https://www.aozora.gr.jp/cards/000879/files/127_15260.html'},
            ],
            contents: '',
       }
   },
   methods: {
      GetText: function(event){
          console.log(event.target.value);
          var req = new XMLHttpRequest();
          req.onreadystatechange = function() {
              if (req.readyState == 4 && req.status == 200){
                  return req.responseText;
              }
          };
          req.open("GET", this.selected, false);
          req.send(null);
      } 
   }
}
</script>
<style scoped>
h1 {
    text-align: center;
}

select {
    margin: 15px auto;
    height: 30px;
}

div#content {
    margin: auto;
    width: 500px;
    height: 800px;
    padding: 20px;
    text-align: left;
    border: solid 1px black;
}
</style>