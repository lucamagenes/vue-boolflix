<template>
  <div id="app">
    <SiteHeader @search-element="search" />
    <SiteMain :films="films" :series="series" />
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";
import SiteMain from "./components/SiteMain.vue";

import axios from "axios";

export default {
  name: "App",
  components: {
    SiteHeader,
    SiteMain,
  },
  data() {
    return {
      films: [],
      series: [],
      error: "",
      movie_url: "https://api.themoviedb.org/3/search/movie",
      tvShow_url: "https://api.themoviedb.org/3/search/tv",
      api_key: "de751d2bf92975ccebd5f3008e453c82",
    };
  },
  methods: {
    search(text) {
      console.log(text);

      axios
        .get(
          `${this.movie_url}?api_key=${this.api_key}&language=it&query=${text}&page=1&include_adult=false`
        )
        .then((response) => {
          console.log(response.data.results);
          this.films = response.data.results;
          console.log(this.films);
        })
        .catch((error) => {
          console.log(error, "OPS!");
          this.error = error;
        });

      axios
        .get(
          `${this.tvShow_url}?api_key=${this.api_key}&language=it&query=${text}&page=1&include_adult=false`
        )
        .then((response) => {
          console.log(response.data.results);
          this.series = response.data.results;
          console.log(this.series);
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
@import "./assets/scss/common.scss";

body {
  background-color: $background-dark-gray;
  color: $font-main-color;
}
</style>
