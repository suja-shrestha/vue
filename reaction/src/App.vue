<template>
  <div class="container">
    <h1>Check Your Reaction</h1>
    <button @click="start" :disabled="isPlaying">Test</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
    <Result v-if="showResult" :score="score"/>
  </div>
</template>

<script>
import Block from './components/Block.vue';
import Result from './components/Result.vue';
export default {
  name: "App",
  components: {Block, Result},
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    } 
  },  
};
</script>

<style scoped>
.container {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin: 20px;
  padding: 20px;
}

h1 {
  font-size: 2.5em;
  margin-bottom: 20px;
}

button {
  font-size: 1.2em;
  padding: 10px 20px;
  margin: 20px;
  cursor: pointer;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 5px;
}

button:disabled {
  cursor: not-allowed;
  background-color: #ccc;
}

@media (max-width: 600px) {
  h1 {
    font-size: 2em;
  }

  button {
    font-size: 1em;
    padding: 8px 16px;
  }
}
</style>
