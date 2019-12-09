<template>
  <div id="app">
    <EViewer />
  </div>
</template>

<script>
import EViewer from './components/EViewer.vue'

export default {
  name: 'app',
  components: {
    EViewer
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
