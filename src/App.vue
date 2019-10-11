<template lang="html">
  <h1>Studio Ghibli Films</h1>
</template>

<script>
import FilmsList from './components/FilmsList.vue';

export default {
  name: 'app',
  data(){
    return {
      films: []
    }
  },
  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)
  },
  components: {
    'films-list': FilmsList
  }
}
</script>

<style lang="css" scoped>
</style>
