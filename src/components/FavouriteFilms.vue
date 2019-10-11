<template lang="html">
  <div>
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
