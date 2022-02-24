<template>
  <div id="app">
    <!-- richiamo componenti all'interno della page -->
      <MyHeader />
      <MyMain />
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
  }
}
</script>

<style lang="scss">
  // Importo regole generali
  @import './assets/style/general.scss'

</style>
