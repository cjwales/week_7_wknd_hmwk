<template lang="html">
  <div class="favourite-box">
    <h4>My Favourites</h4>
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
