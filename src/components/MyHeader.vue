<template>
  <header class="d-flex justify-content-between align-items-center">
    <img src="../assets/img/logo-spotify.png" alt="" />
    <div>
      <select v-model="selectedGenre" @change="$('selectedGenreEvt', selectedGenre)">

        <option value="">Seleziona un genere</option>

        <option v-for="(genre, index) in genresList" :key="index" :value="genre">{{ genre }}</option>

      </select>

    </div>
  </header>
</template>

<script>


export default {
  name: "MyHeader",

  props: { 
            "genresList" : Array
  },
  data() {
    return{
        selectedGenre: ''
    }
  },

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