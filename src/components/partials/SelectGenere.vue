<template>
  <select v-model="selectedOption" class="mx-3" @change="changeOption">
    <option :placeholder="placeholder" value="">
      {{ placeholder || "Select an option" }}
    </option>
    <option v-for="(option, index) in options" :key="index">
      {{ option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "SelectGenere",
  props: ["placeholder", "options"],
  data() {
    return {
      selectedOption: "",
    };
  },
  methods: {
    changeOption() {
      this.$emit("change-option", this.selectedOption);
    },
  },
};
</script>

<style>
</style>