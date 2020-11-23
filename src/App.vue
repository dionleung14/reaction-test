<template>
  <div>
  <img alt="Vue logo" src="./assets/logo.png">
  <Cheeseburger msg="This is Dion taking over, prepare for trouble" :banana="{salt}"/>
  <StartBtn v-on:start-reaction="escape"/>
  <FinishBtn v-on:stop-reaction="quit" />
  <Timer v-bind:time="timeCountUp" />
  </div>
</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'
  import StartBtn from './components/StartBtn.vue'
  import FinishBtn from './components/FinishBtn.vue'
  import Timer from './components/Timer.vue'

  export default {
    name: 'App',
    components: {
      Cheeseburger: HelloWorld,
      StartBtn,
      FinishBtn,
      Timer
    },
    data() {
      return {
        salt: "heyyoooo",
        timeCountUp: 0
      }
    },
    methods: {
      escape(data) {
        console.log("received it in app");
        console.log(data)
        this.start()
      },
      start(){
        setInterval(()=>{this.timeCountUp++},1000)
      },
      quit(data){
        console.log("received stop in app")
        console.log(data)
        clearInterval(this.start)
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
