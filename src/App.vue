<template>
  <img alt="Vue logo" src="./assets/logo.png">
  {{ salt }}
  <Cheeseburger msg="This is dion taking over, prepare for trouble" :banana="{salt}"/>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'

  export default {
    name: 'App',
    components: {
      Cheeseburger: HelloWorld
    },
    data() {
      return {
        salt: "heyyoooo"
      }
    }
  }
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0
}

body {
  background: teal;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
