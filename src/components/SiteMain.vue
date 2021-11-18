<template>
  <main>
    <SearchMoviesBox />
    <MoviesResearch />
  </main>
</template>

<script>
import SearchMoviesBox from "./SearchMoviesBox.vue";
import MoviesResearch from "./MoviesResearch.vue";

export default {
  components: {
    SearchMoviesBox,
    MoviesResearch,
  },
};
</script>

<style lang="scss">
</style>