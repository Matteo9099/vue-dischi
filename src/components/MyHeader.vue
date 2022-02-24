<template>
  <header class="d-flex justify-content-between align-items-center">
    <img src="../assets/img/logo-spotify.png" alt="" />
    <div>
      <SelectGenere
        placeholder="Seleziona un genere"
        :options="genres"
        @change-option="selectedGenres"
      />
    </div>
  </header>
</template>

<script>
import SelectGenere from "./partials/SelectGenere.vue";

export default {
  name: "MyHeader",
  components: {
    SelectGenere,
  },
  props: ["genres"],
  methods: {
    selectedGenres(selectedOption) {
      this.$emit("selected-genre", selectedOption);
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variabili.scss";
    header {
        height: 70px;
        background-color: $bgColorHeader;
        color: white;
    img {
        height: 100%;
        padding: 10px;
    }
    }
</style>