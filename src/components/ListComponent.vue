<template lang="html">
  <div>
    <li v-on:click="handleClick">{{film.title}}</li>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'list-component',
  props: ['film'],
  methods: {
    handleClick() {
      eventBus.$emit('selectedFilm', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
