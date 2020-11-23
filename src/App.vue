<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <Cheeseburger msg="This is Dion taking over, prepare for trouble" :banana="{salt}"/> -->
    <StartBtn v-on:start-reaction="start" />
    <FinishBtn v-on:stop-reaction="quit" />
    <br />
    <button @click="reset">Reset</button>
    <Timer v-bind:time="timeNumber" />
    <br />
    <div v-if="started">
      time number: {{ timeNumber }}
    </div>
    <div v-if="scare">
      Boo
    </div>
  </div>
</template>

<script>
  // import HelloWorld from './components/HelloWorld.vue'
  import StartBtn from "./components/StartBtn.vue";
  import FinishBtn from "./components/FinishBtn.vue";
  import Timer from "./components/Timer.vue";
  export default {
    name: "App",
    components: {
      // Cheeseburger: HelloWorld,
      StartBtn,
      FinishBtn,
      Timer,
    },
    data() {
      return {
        // salt: "heyyoooo",
        timeCounter: setInterval(() => {this.timeNumber++}, 10),
        timeNumber: 0,
        started: false,
        attempts: 0,
        scare: false
      };
    },
    created() {
      clearInterval(this.timeCounter);
    },
    methods: {
      start() {
        if (this.attempts < 2) {
          if (!this.started) {
            this.started = !this.started;
          }
          this.attempts++;
          let randomInt = (Math.random() * 2000) + 2000
          console.log(randomInt / 1000)
          setTimeout( () => {
            this.timeCounter = setInterval(() => {this.timeNumber += 1}, 1)
          }, randomInt)
        } else {
          let randomScare = (Math.random() * 2000) + 2000
          console.log(randomScare / 1000)
          setTimeout( () => {
            this.scare = true
            }, randomScare)
        }
      },
      quit() {
        clearInterval(this.timeCounter);
        this.started = false; 
      },
      reset() {
        this.timeNumber = 0; 
      }
    },
  };
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    text-align: center;
  }

  body {
    background: salmon;
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
