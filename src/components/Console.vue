<template>
  <pre class="console">{{ transformed }}</pre>
</template>

<script>
export default {
  name: 'Console',
  props: ['manipulator', 'input'],
  computed: {
    transformed: function () {
      return this.manipulator(this.input)
    }
  }
}
</script>
<style>
  .console {
    height: 130px;
    width: 230px;
    padding: .5em;
    overflow: scroll;
    box-sizing: border-box;
    word-break: break-word;
    white-space: normal;
    color: lightgreen;
  }
</style>
