<template>
  <div id="app">
    <!--<Buscador/>-->
    <Main/>
  </div>
</template>

<script>
import Main from './components/Main'
//import Buscador from './components/Buscador'

export default {
  name: 'App',
  components: {
    Main
  }
};
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
