<template>
  <div class="card">
    <div class="thumb_image">
      <img
        v-if="film.poster_path"
        :src="'https://image.tmdb.org/t/p/w185/' + film.poster_path"
        alt=""
      />
      <img v-else src="../assets/image-not-found.png" alt="" />
    </div>

    <div class="info_card">
      <div class="title">
        <h3 class="title">{{ film.title }}</h3>
        <p>Titolo originale: {{ film.original_title }}</p>
      </div>

      <div class="languages">
        <span>Lingua originale: </span>
        <span v-if="film.original_language == 'en'">
          <country-flag country="gb" size="normal" />
        </span>
        <span v-else-if="film.original_language == 'it'">
          <country-flag country="it" size="normal" />
        </span>
        <span v-else-if="film.original_language == 'fr'">
          <country-flag country="fr" size="normal" />
        </span>
        <span v-else-if="film.original_language == 'de'">
          <country-flag country="de" size="normal" />
        </span>
        <span v-else-if="film.original_language == 'es'">
          <country-flag country="es" size="normal" />
        </span>
        <span v-else-if="film.original_language == 'ja'">
          <country-flag country="jp" size="normal" />
        </span>
        <span v-else-if="film.original_language == 'zh'">
          <country-flag country="cn" size="normal" />
        </span>
        <span v-else>
          {{ film.original_language }}
        </span>
      </div>

      <div class="rating">
        <span>Voto: </span>
        <span
          v-for="(icon, i) in Math.ceil(film.vote_average / 2)"
          :key="'far' + i"
        >
          <font-awesome-icon :icon="['fas', 'star']" />
        </span>
        <span
          v-for="(icon, i) in 5 - Math.ceil(film.vote_average / 2)"
          :key="'far' + i"
        >
          <font-awesome-icon :icon="['far', 'star']" />
        </span>
      </div>

      <div class="overview">
        <strong>OverView:</strong>
        <span>{{ film.overview.substr(0, 120) + "..." }} </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    film: Object,
  },
};
</script>

<style lang="scss">
.languages {
  display: flex;
  align-items: center;
}
</style>