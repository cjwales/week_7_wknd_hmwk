<template lang="html">
  <form v-on:submit.prevent>
    <select v-on:change="handleSelect" v-model="selectedFilm">
      <option disabled value="">Select a film...</option>
      <option v-for="film in films" :value="film">{{film.title}}</option>
    </select>
  </form>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: "film-form",
  data(){
    return {
      "selectedFilm": []
    }
  },
  props: ['films'],
  methods: {
    handleSelect() {
      eventBus.$emit('film-selected', this.selectedFilm)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
