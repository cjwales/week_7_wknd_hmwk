<template lang="html">
  <div class="master">
    <h1>Studio Ghibli Films</h1>
    <film-form :films="films"></film-form>
    <div class="main-container">
      <film-detail :film="selectedFilm"></film-detail>
      <favourite-films :favourites="favourites"></favourite-films>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'

import FilmForm from './components/FilmForm.vue'
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

    eventBus.$on('filmSelected', (film) => {
      this.selectedFilm = film;
    })

    eventBus.$on('selectedFavourite', (favouritefilm) => {
      this.favourites.push(favouritefilm)
    })
  },
  components: {
    'film-detail': FilmDetail,
    'favourite-films': FavouriteFilms,
    'film-form': FilmForm
  }
}
</script>

<style lang="css" scoped>
.main-container {
  display: flex;
  justify-content: space-around;
  text-align: center;
}

h1 {
  text-align: center;
  font-family: 'PT Serif', serif;
}
</style>
