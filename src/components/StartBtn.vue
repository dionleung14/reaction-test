<template>
  <button v-on:click="$emit('start-reaction', 0)" id="hello">
    Start
  </button>
</template>

<script>
export default {
  methods: {
    pump() {
      // $this.$emit("yes")
    }
  }
}
</script>

<style scoped>
  button {
    color: green;
    padding: 3px;
  }
  #hello {
    background-color: aqua;
  }
</style>