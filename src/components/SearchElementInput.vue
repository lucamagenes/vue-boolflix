<template>
  <div class="searchBox">
    <label for="searchElement">Cerca:</label>
    <input
      type="search"
      name="searchElement"
      id="searchElement"
      placeholder="Titolo film"
      v-model="searchElement"
    />
    <button @click="$emit('search-element', searchElement)">Cerca</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchElement: "",
    };
  },
};
</script>

<style lang="scss">
</style>