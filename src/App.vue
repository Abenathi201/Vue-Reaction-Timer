<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <!-- <p v-if="showResult">Reaction Time: {{ score }} m/s</p> -->
  <Result v-if="showResult" :score="score"/>
</template>

<script>
import Block from './components/BLock.vue'

import Result from './components/Result.vue'

export default {
  name: 'App',

  components: { Block, Result },

  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },

  methods: {
    start () {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResult = false
      // console.log(this.delay);
    },

    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResult = true
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
  margin-top: 60px;
}
</style>
