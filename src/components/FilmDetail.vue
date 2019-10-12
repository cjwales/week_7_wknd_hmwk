<template lang="html">
  <div v-if="film" class="film-detail">
    <h3 class="title">{{film.title}}</h3>
    <h4>{{film.release_date}}</h4>
    <h4>Directed by: {{film.director}}</h4>
    <h4>Produced by: {{film.producer}}</h4>
    <h5>Rotten Tomatoes Score: {{film.rt_score}}</h5>
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
  background-color:rgba(192,192,192,0.7);
}

.title {
  font-family: 'PT Serif', serif;
}

p {
  text-align: left;
  margin: 10px;
}

button {
  background-color: #1ecbe1;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 10px;
  cursor: pointer;
}
</style>
