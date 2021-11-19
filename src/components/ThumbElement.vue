<template>
  <div class="col-3">
    <div class="Thumb">
      <div class="title">
        <h3 class="title">{{ item.title || item.name }}</h3>
        <p>Titolo originale: {{ item.original_title || item.original_name }}</p>
      </div>

      <div class="languages">
        <span v-if="item.original_language == 'en'">
          <country-flag country="en" size="normal" />
        </span>
        <span v-else-if="item.original_language == 'it'">
          <country-flag country="it" size="normal" />
        </span>
        <span v-else-if="item.original_language == 'fr'">
          <country-flag country="fr" size="normal" />
        </span>
        <span v-else-if="item.original_language == 'de'">
          <country-flag country="de" size="normal" />
        </span>
        <span v-else-if="item.original_language == 'es'">
          <country-flag country="es" size="normal" />
        </span>
        <span v-else-if="item.original_language == 'ja'">
          <country-flag country="ja" size="normal" />
        </span>
        <span v-else-if="item.original_language == 'zh'">
          <country-flag country="zh" size="normal" />
        </span>
        <span v-else>
          <p>Lingua originale: {{ item.original_language }}</p>
        </span>
      </div>

      <div class="rating">
        <p>Voto: {{ item.vote_average }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: Object,
  },
};
</script>

<style lang="scss">
</style>