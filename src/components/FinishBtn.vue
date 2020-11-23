<template>
  <button @click="$emit('stop-reaction', 0)">
    Stop
  </button>
</template>

<script>
export default {
  
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
