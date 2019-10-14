<template lang="html">
  <div v-if="this.favourites.length >= 1" class="favourite-box">
    <h4>My Favourites</h4>
    <ul>
      <li v-for="favourite in favourites">
        {{favourite.title}} <span v-on:click="deleteFav(favourite)">❌</span>
      </li>
    </ul>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'favourite-films',
  props: ['favourites'],
  methods: {
    deleteFav(favouriteFilm) {
      eventBus.$emit('favourite-deleted', favouriteFilm)
    }
  }
}
</script>

<style lang="css" scoped>
h4 {
  font-family: 'PT Serif', serif;
}

ul {
  list-style: none;
}

li {
  font-family: 'PT Serif', serif;
}
</style>
