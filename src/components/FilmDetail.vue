<template lang="html">
  <div v-if="film" class="film-detail">
    <h3>{{film.title}}</h3>
    <h4>{{film.release_date}}</h4>
    <h4>Directed by: {{film.director}}</h4>
    <h4>Produced by: {{film.producer}}</h4>
    <p>Rotten Tomatoes Score: {{film.rt_score}}</p>
    <p>Description: {{film.description}}</p>
    <button v-on:click="handleClick" type="button" name="add-favourite">Add to Favourites</button>
  </div>
</template>

<script>
import {eventBus} from '../main.js';
import FavouriteFilms from './FavouriteFilms.vue';

export default {
  name: 'film-detail',
  props: ['film'],
  components: {
    'favourite-films': FavouriteFilms
  },
  methods: {
    handleClick() {
      eventBus.$emit('selectedFavourite', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
.film-detail {
  max-width: 300px;
}
</style>
