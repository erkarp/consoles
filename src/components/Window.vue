<template>
  <div>
    <input v-model="text">
    <pre>{{ text }}</pre>
    <Console
      v-for="manipulator in manipulators"
      v-bind:manipulator="manipulator.fn"
      v-bind:key="manipulator.id"
      v-bind:input="text"
    ></Console>
  </div>
</template>

<script>
import Console from './Console'

export default {
  name: 'Window',
  components: {
    Console
  },
  data () {
    return {
      text: '',
      manipulators: [
        {
          id: 0,
          fn: s => {
            return s.split('').reverse().join('')
          }
        },
        {
          id: 1,
          fn: s => {
            return s.toUpperCase()
          }
        },
        {
          id: 2,
          fn: s => {
            return s.toLowerCase()
          }
        },
        {
          id: 3,
          fn: s => {
            return s.split(' ').reverse().join(' ')
          }
        }
      ]
    }
  }
}
</script>
