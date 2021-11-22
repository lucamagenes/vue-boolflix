<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="logo">
          <h1>BOOLFLIX</h1>
        </div>
        <div class="tool">
          <!-- <SearchElementInput @search-element="search" /> -->
          <div class="searchBox">
            <input
              type="search"
              name="searchElement"
              id="searchElement"
              placeholder="Cerca"
              v-model="searchElement"
              @keydown.enter="$emit('search-element', searchElement)"
            />
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
//import SearchElementInput from "./SearchElementInput.vue";

export default {
  components: {
    //SearchElementInput,
  },
  data() {
    return {
      searchElement: "",
    };
  },
};
</script>

<style lang="scss">
@import "../assets/scss/common.scss";
.logo {
  h1 {
    color: $brand-color-text;
  }
}
</style>