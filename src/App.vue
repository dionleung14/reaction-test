<template>
  <div class="flex">
    <div v-if="!startClicked">
      <StartBtn v-on:start-reaction="start" />
    </div>
    <div>
      <FinishBtn v-on:stop-reaction="quit" />
    </div>
    <div>
      <ResetBtn v-on:reset="reset" />
    </div>
    <br />
    <div v-if="started">
      <!-- <Timer v-bind:time="timeNumber" /> -->
      <Timer v-bind:time="timeNumber / 100 + 's'" />
      <!-- <Timer v-bind:time="timeNumber % 100" />
      <Timer v-bind:time="timeNumber % 10" /> -->
    </div>
    <div v-if="scare">
      <JumpScare />
    </div>
  </div>
</template>

<script>
  // import HelloWorld from './components/HelloWorld.vue'
  import StartBtn from "./components/StartBtn.vue";
  import FinishBtn from "./components/FinishBtn.vue";
  import ResetBtn from "./components/ResetBtn.vue";
  import Timer from "./components/Timer.vue";
  import JumpScare from "./components/JumpScare.vue";

  export default {
    name: "App",
    components: {
      // Cheeseburger: HelloWorld,
      StartBtn,
      FinishBtn,
      Timer,
      JumpScare,
      ResetBtn,
    },
    data() {
      return {
        // salt: "heyyoooo",
        timeCounter: setInterval(() => {
          this.timeNumber++;
        }, 10),
        timeNumber: 0,
        started: false,
        startClicked: false,
        attempts: 0,
        limit: 1,
        scare: false,
      };
    },
    created() {
      clearInterval(this.timeCounter);
    },
    methods: {
      start() {
        if (!this.startClicked) {
          this.startClicked = !this.startClicked;
        }
        if (this.attempts <= this.limit) {
          this.attempts++;
          let randomInt = Math.random() * 2000 + 2000;
          console.log(randomInt / 1000);
          setTimeout(() => {
            this.timeCounter = setInterval(() => {
              if (!this.started) {
                this.started = !this.started;
              }
              this.timeNumber += 1;
            }, 1);
          }, randomInt);
        }
        // else {
        //   let randomScare = (Math.random() * 2000) + 2000
        //   console.log(randomScare / 1000)
        //   setTimeout( () => {
        //     this.scare = true
        //     }, randomScare)
        // }
      },
      quit() {
        clearInterval(this.timeCounter);
        if (this.attempts > this.limit) {
          this.scare = true;
        }
      },
      reset() {
        this.started = false;
        this.timeNumber = 0;
      },
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
  .flex {
    display: flex;
    justify-content: space-around;
  }
</style>
