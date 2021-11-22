<template>
  <div class="card">
    <div class="thumb_image">
      <img
        v-if="serie.poster_path"
        :src="'https://image.tmdb.org/t/p/w185/' + serie.poster_path"
        alt=""
      />
      <img v-else src="../assets/image-not-found.png" alt="" />
    </div>
    <div class="title">
      <h3 class="title">{{ serie.name }}</h3>
      <p>Titolo originale: {{ serie.original_name }}</p>
    </div>

    <div class="languages">
      <span v-if="serie.original_language == 'en'">
        <country-flag country="gb" size="normal" />
      </span>
      <span v-else-if="serie.original_language == 'it'">
        <country-flag country="it" size="normal" />
      </span>
      <span v-else-if="serie.original_language == 'fr'">
        <country-flag country="fr" size="normal" />
      </span>
      <span v-else-if="serie.original_language == 'de'">
        <country-flag country="de" size="normal" />
      </span>
      <span v-else-if="serie.original_language == 'es'">
        <country-flag country="es" size="normal" />
      </span>
      <span v-else-if="serie.original_language == 'ja'">
        <country-flag country="jp" size="normal" />
      </span>
      <span v-else-if="serie.original_language == 'zh'">
        <country-flag country="cn" size="normal" />
      </span>
      <span v-else>
        <p>Lingua originale: {{ serie.original_language }}</p>
      </span>
    </div>

    <div class="rating">
      <span
        v-for="(icon, i) in Math.ceil(serie.vote_average / 2)"
        :key="'far' + i"
      >
        <font-awesome-icon :icon="['fas', 'star']" />
      </span>
      <span
        v-for="(icon, i) in 5 - Math.ceil(serie.vote_average / 2)"
        :key="'far' + i"
      >
        <font-awesome-icon :icon="['far', 'star']" />
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    serie: Object,
  },
};
</script>

<style lang="scss">
</style>