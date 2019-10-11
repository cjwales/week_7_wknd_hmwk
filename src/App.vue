<template lang="html">
  <div>
    <h1>Studio Ghibli Films</h1>
    <div class="main-container">
      <films-list :films="films"></films-list>
      <film-detail :film="selectedFilm"></film-detail>
      <favourite-films :favourites="favourites"></favourite-films>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'

import FilmsList from './components/FilmsList.vue';
import ListComponent from './components/ListComponent.vue';
import FilmDetail from './components/FilmDetail.vue';
import FavouriteFilms from './components/FavouriteFilms.vue';

export default {
  name: 'app',
  data(){
    return {
      films: [],
      favourites: [],
      selectedFilm: null
    }
  },
  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('selectedFilm', (film) => {
      this.selectedFilm = film;
    })

    eventBus.$on('selectedFavourite', (favouriteFilm) => {
      this.favourites.push(favouritefilm)
    })
  },
  components: {
    'films-list': FilmsList,
    'list-component': ListComponent,
    'film-detail': FilmDetail,
    'favourite-films': FavouriteFilms
  }
}
</script>

<style lang="css" scoped>
.main-container {
  display: flex;
}
</style>
