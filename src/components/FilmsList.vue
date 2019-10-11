<template lang="html">
  <div>
    <ul>
      <list-component v-for="film in films" :film="film"></list-component>
    </ul>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue'

export default {
  name: "films-list",
  props: ['films'],
  components: {
    'list-component': ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
