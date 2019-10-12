<template lang="html">
  <div v-if="this.favourites.length >= 1" class="favourite-box">
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
