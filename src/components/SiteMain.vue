<template>
  <main>
    <div class="container">
      <div class="tool">
        <SearchMoviesBar @search-movie="search" />
      </div>
      <div class="row" v-if="movies.length">
        <MovieElement :movie="movie" v-for="movie in movies" :key="movie.id" />
      </div>
      <div class="nothing" v-else>
        <h1>
          Per iniziare una ricerca inserisci il nome di un film nella barra di
          ricerca
        </h1>
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
      movie_url: "https://api.themoviedb.org/3/search/movie",
      api_key: "de751d2bf92975ccebd5f3008e453c82",
    };
  },
  methods: {
    search(text) {
      console.log(text);

      const full_movie_url = `${this.movie_url}?api_key=${this.api_key}&language=it&query=${text}&page=1&include_adult=false`;

      var config = {
        method: "get",
        url: full_movie_url,
      };

      axios(config)
        .then((response) => {
          console.log(response.data.results);
          this.movies = response.data.results;
          console.log(this.movies);
        })
        .catch((error) => {
          console.log(error, "OPS!");
          this.error = error;
        });
    },
  },
};
</script>

<style lang="scss">
</style>