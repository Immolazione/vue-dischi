<template>
<header class="w-100 d-flex align-items-center">
    <img class="ms-3" src="../assets/img/spotify.png" alt="Spotify Icon">
</header>
</template>

<script>
export default {
  name: 'Header',
}
</script>


<style scoped lang="scss">
@import '../assets/scss/style.scss';
header {
  position: fixed;
  height: 5rem;
  background-color: $header-color;
  img {
    width: 4rem;
  }
}
</style>
