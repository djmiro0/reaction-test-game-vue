<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    CLICK ME!
  </div>
</template>

<script>
export default {
  name: 'Block',
  props: ["delay"],
  data() {
    return {
      showBlock: null,
      reactionTime: 0
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    }, this.delay)
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10
      }, 10)
    },
    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime)
    }
  }
}
</script>

<style scoped>
.block {
  width: 280px;
  height: 180px;
  display: flex;
  margin-top: 100px;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #00FFC6, #0075FF);
  color: #fff;
  font-size: 24px;
  font-weight: bold;
  font-family: 'Orbitron', sans-serif;
  border-radius: 20px;
  box-shadow: 0 0 20px rgba(0, 255, 198, 0.6);
  cursor: pointer;
  user-select: none;
  animation: pulse 1.2s infinite ease-in-out;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.block:hover {
  transform: scale(1.05);
  box-shadow: 0 0 30px rgba(0, 255, 198, 0.8);
}

@keyframes pulse {

  0%,
  100% {
    box-shadow: 0 0 20px rgba(0, 255, 198, 0.6);
  }

  50% {
    box-shadow: 0 0 35px rgba(0, 255, 198, 0.9);
  }
}
</style>
