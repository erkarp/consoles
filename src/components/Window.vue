<template>
  <div>
    <input v-model="text">
    <pre>{{ text }}</pre>
    <Console
      v-for="manipulator in manipulators"
      v-bind:manipulator="manipulator"
      v-bind:key="manipulators.indexOf(manipulator)"
      v-bind:input="text"
    ></Console>
  </div>
</template>

<script>
import manipulators from 'manipulators'
import Console from './Console'

const capitalize = ['Second', 'Third', 'Fourth', 'Fifth', 'Sixth', 'Seventh']
  .reduce((object, current, index) => {
    object[`every${current}Character`] = s => {
      return manipulators.capitalize.every(index + 2, s)
    }
    return object
  }, {})

export default {
  name: 'Window',
  components: {
    Console
  },
  data () {
    return {
      text: '',
      manipulators: [
        capitalize.everySecondCharacter,
        capitalize.everySeventhCharacter,
        manipulators.capitalize.randomly
      ]
    }
  }
}
</script>
