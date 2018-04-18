<template>
  <div id="app">
    <YandexSearch/>
  </div>
</template>

<script>
import '../node_modules/bootstrap/dist/css/bootstrap.min.css'
import YandexSearch from './components/YandexSearch'

export default {
  name: 'App',
  components: {
    YandexSearch
  }
}
</script>

<style>
/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
</style>
