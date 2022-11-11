<template>
  <div @click="EndGame">Click me asap!</div>
</template>
<script>
export default {
  name: "Block",
  data() {
    return {
      countStart: 0,
      countEnd: 0,
      time: 0,
    };
  },
  methods: {
    EndGame() {
      this.time = Date.now() - this.countStart;
      this.$emit("terminate", this.time);
    },
  },
  mounted() {
    this.countStart = Date.now();
  },
};
</script>
<style scoped>
div {
  width: 400px;
  height: 400px;
  background-color: green;
  margin-top: 20px;
  border-radius: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
</style>
