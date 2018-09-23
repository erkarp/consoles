<template>
  <div id="app">
    <Window/>
  </div>
</template>

<script>
import Window from './components/Window'

export default {
  name: 'App',
  components: {
    Window
  }
}
</script>

<style>
html {
  background-color: #000;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
  text-align: center;
  color: #2c3e50;
  background-color: #000;
}
</style>
