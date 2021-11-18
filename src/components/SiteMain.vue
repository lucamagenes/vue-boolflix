<template>
  <main>
    <div class="container">
      <div class="tool">
        <SearchMoviesBar />
      </div>
      <div class="row">
        <MovieElement
          :movie="movie"
          v-for="movie in movies"
          :key="movie.title"
        />
      </div>
    </div>
  </main>
</template>

<script>
import SearchMoviesBar from "./SearchMoviesBar.vue";
import MovieElement from "./MovieElement.vue";

import axios from "axios";

export default {
  components: {
    SearchMoviesBar,
    MovieElement,
  },
  data() {
    return {
      movies: [],
      error: "",
    };
  },
  mounted() {
    var config = {
      method: "get",
      url: "https://api.themoviedb.org/3/search/movie?api_key=de751d2bf92975ccebd5f3008e453c82&language=it&query=fight&page=1&include_adult=false",
    };

    axios(config)
      .then(function (response) {
        console.log(response.data.results);
        this.movies = response.data.results;
      })
      .catch(function (error) {
        console.log(error, "OPS!");
        this.error = error;
      });
  },
};
</script>

<style lang="scss">
</style>