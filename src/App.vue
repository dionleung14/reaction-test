<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Cheeseburger msg="This is dion taking over, prepare for trouble" banana="9"/>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'

  export default {
    name: 'App',
    components: {
      Cheeseburger: HelloWorld
    }
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
