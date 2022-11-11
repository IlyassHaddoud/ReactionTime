<template>
  <h1>Reaction timer</h1>
  <button @click="play">Play</button>
  <Block v-if="isPlaying" />
</template>

<script>
import Block from "./components/Block";
import Result from "./components/Result";
export default {
  name: "App",
  components: { Block, Result },
  data() {
    return {
      isPlaying: false,
    };
  },
  methods: {
    play() {
      this.isPlaying = true;
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
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
button {
  width: 100px;
}
</style>
