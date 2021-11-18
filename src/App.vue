<template>
  <div id="app">
    <site-header />
    <SiteMain />
    <site-footer />
  </div>
</template>

<script>
import SiteMain from "./components/SiteMain.vue";
export default {
  name: "App",
  components: {
    SiteMain,
  },
};
</script>

<style lang="scss">
@import "./assets/scss/common.scss";
</style>
