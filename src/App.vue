<template>
  <div>
  <img alt="Vue logo" src="./assets/logo.png">
  {{ salt }}
  <Cheeseburger msg="This is Dion taking over, prepare for trouble" :banana="{salt}"/>
  <StartBtn />
  <FinishBtn />
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'
  import StartBtn from './components/StartBtn.vue'
  import FinishBtn from './components/FinishBtn.vue'

  export default {
    name: 'App',
    components: {
      Cheeseburger: HelloWorld,
      StartBtn,
      FinishBtn
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
  background: salmon;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
