<template>
  <div id="app">
    <!-- richiamo componenti all'interno della page -->
      <MyHeader :genresList="genreList" @selectedGenreEvt="setSelectedGenre"/>
      <MyMain @genresReady="setGenres" :selectedGenre="selectedGenre" />
  </div>
</template>

<script>
  import MyHeader from './components/MyHeader.vue'
  import MyMain from './components/MyMain.vue'
 

export default {
  name: 'App',
  components: {
    // componenti da aggiungere
      MyHeader,
      MyMain
  },
  data(){
      return{
        genresList: [],
        selectedGenre: ''
      }
  },
  methods: {
      setGenres(genresListEvt) {
        this.genresList = genresListEvt;
      },
      setSelectedGenre(selectedGenreEvt) {
        this.selectedGenre = selectedGenreEvt;
      }
  }
}
</script>

<style lang="scss">
  // Importo regole generali
  @import './assets/style/general.scss'

</style>
