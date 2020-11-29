<template>
  <button @click="$emit('start-reaction', 0)" id="hello">
    Start
  </button>
</template>

<script>
export default {
  
}
</script>

<style scoped>
  button {
    color: green;
    padding: 10px;
    font-size: 20px;
  }
  #hello {
    background-color: aqua;
  }
  #hello:hover {
    background-color: blue;
    cursor: pointer;
  }
</style>