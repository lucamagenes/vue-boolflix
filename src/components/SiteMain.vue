<template>
  <main>
    <div class="container">
      <div class="tool">
        <SearchElementInput @search-element="search" />
      </div>
      <div class="row" v-if="items.length">
        <h1>Film e Serie TV</h1>
        <div class="Movies row">
          <ThumbElement :item="item" v-for="item in items" :key="item.id" />
        </div>
      </div>
      <div class="nothing" v-else>
        <h2>
          Per iniziare una ricerca inserisci il nome di un film nella barra di
          ricerca
        </h2>
      </div>
    </div>
  </main>
</template>

<script>
import SearchElementInput from "./SearchElementInput.vue";
import ThumbElement from "./ThumbElement.vue";

import axios from "axios";

export default {
  components: {
    SearchElementInput,
    ThumbElement,
  },
  data() {
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
  },
};
</script>

<style lang="scss">
</style>