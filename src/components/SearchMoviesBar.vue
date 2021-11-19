<template>
  <div class="searchBox">
    <label for="searchMovies">Cerca:</label>
    <input
      type="search"
      name="searchMovies"
      id="searchMovies"
      placeholder="Titolo film"
      v-model="searchMovie"
    />
    <button @click="$emit('search-movie', searchMovie)">Cerca</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchMovie: "",
    };
  },
};
</script>

<style lang="scss">
</style>