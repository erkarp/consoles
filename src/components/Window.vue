<template>
  <div>
    <input v-model="text">
    <Console
      v-for="[index, manipulator] in manipulators.entries()"
      v-bind:transformer="manipulator" v-bind:key="index"
     ></Console>
  </div>
</template>

<script>
import Console from './components/Console'
  
export default {
  name: 'Window',
  data () {
    return {
      text: input, 
      manipulators: [
        { id: 0, fn: 'Vegetables' },
        { id: 1, fn: 'Cheese' },
        { id: 2, fn: 'Whatever else humans are supposed to eat' }
      ]
    }
  }
}
</script>