<template>
  <div class="col-3">
    <div class="movieThumb">
      <h3 class="title">{{ movie.title }}</h3>
      <p>
        Titolo originale: {{ movie.original_title }}
        <br />
        Lingua: {{ movie.original_language }}
        <br />
        Voto: {{ movie.vote_average }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object,
  },
};
</script>

<style lang="scss">
</style>