<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="logo">
          <h1>BOOLFLIX</h1>
        </div>
        <div class="tool">
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
export default {
  data() {
    return {
      searchElement: "",
    };
  },
};
</script>

<style lang="scss">
@import "../assets/scss/common.scss";

header {
  margin-bottom: 4rem;
  .container {
    .row {
      height: 60px;
      justify-content: space-between;
      align-items: center;
      .logo {
        h1 {
          color: $brand-color;
        }
      }
      .searchBox {
        input {
          height: 30px;
          font-size: 1.2rem;
          background-color: $background-dark-gray;
          border: 1px solid white;
          color: white;
          padding: 0 1rem;
        }
      }
    }
  }
}
</style>