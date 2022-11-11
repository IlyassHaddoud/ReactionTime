<template>
  <h1>Reaction timer</h1>
  <button @click="play" ref="btn" :disable="isPlaying">Play</button>
  <Block v-if="isPlaying" @terminate="getResult" />
  <Result v-if="terminate" :ReactionTime="result" />
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
      terminate: false,
      delay: this.getDelay(),
      result: 0,
    };
  },
  methods: {
    getDelay() {
      return 1000 + Math.random() * 3000;
    },

    play() {
      this.terminate = false;
      this.$refs.btn.classList.add("disable");
      setTimeout(() => {
        this.isPlaying = true;
      }, this.delay);
    },

    getResult(result) {
      this.$refs.btn.classList.remove("disable");
      this.isPlaying = false;
      this.terminate = true;
      this.result = result;
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
  background-color: green;
  color: white;
  border-style: none;
  padding: 7px;
  border-radius: 5px;
}
.disable {
  background-color: gray;
  cursor: not-allowed;
}
</style>
