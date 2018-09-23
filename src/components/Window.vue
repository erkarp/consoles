<template>
  <div>
    <div>
      <input v-model="text" ref="text">
    </div>
    <div v-on:click="focus()" class="window">
      <Console
        v-for="manipulator in manipulators"
        v-bind:manipulator="manipulator"
        v-bind:key="manipulators.indexOf(manipulator)"
        v-bind:input="text"
      ></Console>
    </div>
  </div>
</template>

<style>
  .window {
    display: inline-flex;
    justify-content: space-between;
    flex-wrap: wrap;
    width: 1000px;
    text-align: left;
  }

  @media (max-width: 1000px) {
    .window {
      width: 100%;
      justify-content: space-evenly;
    }
  }
  /* input {
    display: none;
  } */
</style>

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

const customReverse = (on, s) => {
  return s.split(on).reverse().join(on)
}

export default {
  name: 'Window',
  components: { Console },
  data () {
    return {
      text: '',
      manipulators: [
        capitalize.everySecondCharacter,
        s => { return customReverse('e', s) },
        capitalize.everySeventhCharacter,
        s => { return customReverse(' ', s) },
        manipulators.capitalize.randomly,
        s => { return customReverse('', s) },
        capitalize.everySixthCharacter,
        capitalize.everyThirdCharacter
      ]
    }
  },
  methods: {
    focus: function () {
      this.$refs.text.focus()
    }
  }
}
</script>
