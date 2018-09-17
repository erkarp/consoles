<template>
  <div class="console">{{ transformed }}</div>
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
    margin: 10px;
  }
</style>
