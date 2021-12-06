<template>
  <div>
    <p v-if="age > 25">{{ msg }}</p>
    <p v-else>You must be 25 year or older to view this message</p>
  </div>
</template>

<script>
export default {
  name: "Greeting",
  props: ["age"],
  data() {
    return {
      msg: "Helloworld",
    };
  },
};
</script>

<style scoped>
p {
  color: red;
}
</style>
