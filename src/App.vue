<template>
  <div id="app">
    <Header @searchDone="search" />
    <Main :MovieList="moviesArray"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data: function () {
    return {
      queryValue:'',
      apiKey: '3bb317aa05deaa854d0f2a5d7e51265c',
      moviesArray: []
    };
  },
  methods: {
    search: function (userString) {
      this.queryValue = userString;
      this.getMovies();
      console.log();
    },
    getMovies: function () {
      axios.get(
        'https://api.themoviedb.org/3/search/movie',
        {
          params: {
            api_key: '3bb317aa05deaa854d0f2a5d7e51265c',
            query: this.queryValue,
          }
        }
      ).then((response) => {
        this.moviesArray = response.data.results;
      });
    },
  }
};
</script>

<style lang="scss">

</style>
