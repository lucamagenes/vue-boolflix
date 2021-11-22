<template>
  <main>
    <div class="container">
      <div class="movies">
        <h2 v-if="films.length">Film</h2>
        <div class="row">
          <div class="film" v-for="film in films" :key="film.id">
            <Film :film="film" />
          </div>
        </div>
        <div class="serie_tv">
          <h2 v-if="series.length">Serie TV</h2>
          <div class="row">
            <div class="serieTv" v-for="serie in series" :key="serie.id">
              <TvSerie :serie="serie" />
            </div>
          </div>
        </div>
      </div>
      <div class="nothing" v-if="films.length == 0 && series.length == 0">
        <h2>Inserisci il nome di un FILM o di una SERIE TV</h2>
      </div>
    </div>
  </main>
</template>

<script>
import Film from "./Film.vue";
import TvSerie from "./TvSerie.vue";

export default {
  components: {
    Film,
    TvSerie,
  },
  props: {
    films: Array,
    series: Array,
  },
};
</script>

<style lang="scss">
main {
  .container {
    h2 {
      margin-bottom: 2rem;
    }
    .row {
      margin-bottom: 3rem;
      justify-content: flex-start;
      flex-wrap: wrap;
      gap: 1rem;
    }
  }
}
</style>