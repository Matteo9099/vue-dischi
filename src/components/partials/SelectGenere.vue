<template>
  <select class="mx-3" @change="changeOption">
    <option value="">Seleziona un genere</option>
    <option v-for="(option, index) in options" :key="index" :value="option">{{ option }}</option>
  </select>
</template>

<script>
export default {
  name: "SelectGenere",
  props: ["options"],
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