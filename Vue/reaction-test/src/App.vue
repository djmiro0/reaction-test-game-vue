<template>
  <img alt="Vue logo" src="./assets/logo.png" width="100px" height="100px">
  <h1>Fast Reaction Game</h1>
  <button class="button" @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results :reactionTime="score" v-if="showResults" />
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  components: {
    Block,
    Results
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.showResults = true
      this.isPlaying = false
    }

  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@600&display=swap');

#app {
  font-family: 'Orbitron', sans-serif;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  color: #00ffc6;
  background-color: #0f0f0f;
  height: 100vh;
  padding: 30px;
}

img {
  filter: drop-shadow(0 0 10px #00ffc6);
  margin-bottom: 20px;
}

h1 {
  font-size: 2.5rem;
  color: #ffffff;
  text-shadow: 0 0 10px #00ffc6, 0 0 20px #0075ff;
  margin-bottom: 30px;
}

.button {
  background: linear-gradient(135deg, #00ffc6, #0075ff);
  color: #0f0f0f;
  width: 140px;
  padding: 14px 20px;
  font-size: 1rem;
  font-weight: bold;
  border: none;
  border-radius: 30px;
  cursor: pointer;
  box-shadow: 0 0 10px rgba(0, 255, 198, 0.5);
  transition: all 0.3s ease;
}

.button:hover:enabled {
  transform: scale(1.05);
  box-shadow: 0 0 20px rgba(0, 255, 198, 0.9);
}

.button:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}
</style>
