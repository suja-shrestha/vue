<template>
  <h1>Check Your Reaction</h1>
  <button @click="start" :disabled="isPlaying">Test</button>
  <Block v-if="isPlaying" :delay="delay"/>
</template>
<script>
import Block from './components/Block.vue';
export default {
  name: "App",
  components: {Block},
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = Math.floor(Math.random() * 5000) + 2000;
      console.log(this.delay);
    },
  },  
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  background-color: #4caf50; /* Green */
  border: none;
  color: white;
  padding: 10px 25px;
  text-align: center;
  border-radius: 5px;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}
</style>
