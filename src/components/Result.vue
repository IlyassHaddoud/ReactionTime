<template>
  <div>
    <h3>Reaction Time - {{ ReactionTime }} ms</h3>
    <p v-if="ReactionTime < 300">{{ messages[0] }}</p>
    <p v-else-if="ReactionTime < 500">{{ messages[1] }}</p>
    <p v-else>{{ messages[2] }}</p>
  </div>
</template>
<script>
export default {
  name: "Result",
  props: ["ReactionTime"],
  data() {
    return {
      messages: ["Great", "Not bad ,try again", "Are you retarded ?"],
    };
  },
};
</script>
<style scoped>
p {
  color: green;
  font-weight: bold;
  font-size: large;
}
</style>
