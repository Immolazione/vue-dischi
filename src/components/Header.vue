<template>
<header class="w-100 d-flex align-items-center">
  <div class="w-50 d-flex justify-content-between align-items-center">
    <img class="ms-3" src="../assets/img/spotify.png" alt="Spotify Icon">
    <SearchBar placeholder="Choose a Genre:" :options="genres" @change-option="selectedGenre" />
  </div>
</header>
</template>

<script>
import SearchBar from './SearchBar.vue'
export default {
  name: 'Header',
  components: {
    SearchBar
  },
  props: ['genres'],
  methods: {
    selectedGenre(selectedOption){
      this.$emit('selected-genre', selectedOption);
    },
  },
}
</script>


<style scoped lang="scss">
@import '../assets/scss/style.scss';
header {
  background-color: $header-color;
  height: 5rem;
  position: fixed;
  img {
    width: 4rem;
  }
}
</style>
