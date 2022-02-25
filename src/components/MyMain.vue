<template>
  <main>
    <section id="albums" class="container">
      <div
        class="album-card-container"
        v-for="(album, index) in filteredAlbums"
        :key="index"
      >
        <CardComponents
          :title="album.title"
          :poster="album.poster"
          :author="album.author"
          :year="album.year"
        />
      </div>
    </section>
  </main>
</template>

<script>
import CardComponents from "./partials/CardComponents.vue";
import axios from "axios";

export default {
  name: "MyMain",
  props: {
            "selectedGenre": String
  },
  components: {
    CardComponents,
  },

  data() {
    return {
      albums: [],
    };
  },

  computed: {

    filteredAlbums() {
      if (!this.selectedGenre) return this.albums;
      return this.albums.filter((album) => {
        return album.genre = this.selectedGenre;
      });
    },

  },

  methods: {

    fetchAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.albums = res.data.response;
          const genres = [];
          this.albums.forEach((album) => {
            const genre = album.genre;
            if (!genres.includes(genre)) genres.push(genre);
          });
          this.$emit("genresReady", genres);
        });
    },
  },

  created() {
    this.fetchAlbums();
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variabili.scss";

    main{
        background-color: $bgColorMain;
    
        #albums {
            display: flex;
            flex-wrap: wrap;
            padding: 50px 0;
        }

        .album-card-container {
            width: calc(100% / 5);
        }
    }
</style>