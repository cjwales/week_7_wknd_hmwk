<template lang="html">
  <ul>

  </ul>
</template>

<script>
export default {
  name: "films-list",
  data(){
    return {
      "selectedFilm": []
    }
  },
  props: ['films']
}
</script>

<style lang="css" scoped>
</style>
