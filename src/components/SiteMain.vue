<template>
  <main>
    <div class="container">
      <!-- <div class="tool">
        <SearchElementInput @search-element="search" />
      </div> -->
      <div class="movie">
        <h2 v-if="films.length">Film</h2>
        <div class="row">
          <div class="item row" v-for="film in films" :key="film.id">
            <Film :film="film" />
          </div>
        </div>
        <div class="serie_tv">
          <h2 v-if="series.length">Serie TV</h2>
          <div class="row">
            <div class="serieTv" v-for="serie in series" :key="serie.id">
              <TvSerie :serie="serie" />
            </div>
          </div>
        </div>
      </div>
      <div class="nothing" v-if="films.length == 0 && series.length == 0">
        <h2>Inserisci il nome di un FILM o di una SERIE TV</h2>
      </div>
    </div>
  </main>
</template>

<script>
//import SearchElementInput from "./SearchElementInput.vue";
import Film from "./Film.vue";
import TvSerie from "./TvSerie.vue";

//import axios from "axios";

export default {
  components: {
    //SearchElementInput,
    Film,
    TvSerie,
  },
  props: {
    films: Array,
    series: Array,
  },
  /*  data() {
    return {
      items: [],
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
          this.items = response.data.results;
          console.log(this.items);
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
          this.items = response.data.results;
          console.log(this.items);
        })
        .catch((error) => {
          console.log(error, "OPS!");
          this.error = error;
        });
    },
  }, */
};
</script>

<style lang="scss">
</style>