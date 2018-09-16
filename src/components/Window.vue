<template>
  <div>
    <input v-model="text">
    <pre>{{ text }}</pre>
    <Console
      v-for="[index, manipulator] in manipulators.entries()"
      v-bind:transformer="manipulator"
      v-bind:key="index"
    ></Console>
  </div>
</template>

<script>
// import Console from './Console'

export default {
  name: 'Window',
  data () {
    return {
      text: '',
      manipulators: [
        { id: 0, fn: 'Vegetables' },
        { id: 1, fn: 'Cheese' },
        { id: 2, fn: 'Whatever else humans are supposed to eat' }
      ]
    }
  }
}
</script>
