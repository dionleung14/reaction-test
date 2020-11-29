<template>
  <button @click="$emit('reset', 'yes')">
    Reset
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
    font-size: 20px;
  }
</style>