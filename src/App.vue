<template>
  <div id="app">
    <MyHeader :genresList="genres" />
    <MyMain @genresReady="getGenresList" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      genres: []
    }
  },
  methods: {
    getGenresList(genres) {
      this.genres = genres;
    }
  }
}
</script>

<style lang="scss">
@import './styles/general.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>