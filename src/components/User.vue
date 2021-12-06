<template>
  <div>
    <button type="button" @click="onClickAge">Update age Event</button>
    <button type="button" @click="ageChangeFn(4)">Update age CB</button>
    <p>The user is {{ age }} year old</p>
    <p>{{ ageDoubled }}</p>
  </div>
</template>

<script>
export default {
  name: "User",
  props: {
    age: {
      type: Number,
      // required: true,
      // default: 20,
      validator(value) {
        // this.onClickAge();
        return value < 130;
      },
    },
    ageChangeFn: Function,
  },
  emit: ["age-change"],
  computed: {
    ageDoubled() {
      return this.age * 2;
    },
  },
  methods: {
    onClickAge() {
      this.$emit("age-change", 3);
    },
  },
};
</script>

<style></style>
