<template>
  <div class="col-3">
    <div class="movieThumb">
      <div class="title">
        <h3 class="title">{{ movie.title }}</h3>
        <p>Titolo originale: {{ movie.original_title }}</p>
      </div>

      <div class="languages">
        <span v-if="movie.original_language == 'en'">
          <country-flag country="en" size="normal" />
        </span>
        <span v-else-if="movie.original_language == 'it'">
          <country-flag country="it" size="normal" />
        </span>
        <span v-else-if="movie.original_language == 'fr'">
          <country-flag country="fr" size="normal" />
        </span>
        <span v-else-if="movie.original_language == 'de'">
          <country-flag country="de" size="normal" />
        </span>
        <span v-else-if="movie.original_language == 'es'">
          <country-flag country="es" size="normal" />
        </span>
        <span v-else-if="movie.original_language == 'ja'">
          <country-flag country="ja" size="normal" />
        </span>
        <span v-else-if="movie.original_language == 'zh'">
          <country-flag country="zh" size="normal" />
        </span>
        <span v-else>
          <p>Lingua: {{ movie.original_language }}</p>
        </span>
      </div>

      <div class="rating">
        <p>Voto: {{ movie.vote_average }}</p>
      </div>
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