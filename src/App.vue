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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
