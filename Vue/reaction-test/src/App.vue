<template>
  <img alt="Vue logo" src="./assets/logo.png" width="100px" height="100px">
  <h1>Fast Reaction Game</h1>
  <button class="button" @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" />
</template>

<script>
import Block from './components/Block.vue'

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
    Block
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #2c3e50;
  margin-top: 60px;
}

.button {
  margin: 50px 0;
  background: rgb(26, 211, 171);
  width: 100px;
  padding: 10px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  border-radius: 30px;
}
</style>
