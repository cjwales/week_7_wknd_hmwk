<template lang="html">
  <div>
    <h4>Favourite Films</h4>
    <ul>
      <li v-for="favourite in favourites">{{favourite.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-films',
  props: ['favourites']
}
</script>

<style lang="css" scoped>
</style>
