<template>
<main class="d-flex align-items-center">
    <img src="../assets/img/spotify.png" alt="Spotify Icon">
</main>
</template>

<script>
export default {
  name: 'Main',

}
</script>

<style lang="scss">
@import '../assets/scss/_vars.scss';
    main {
        height: 5rem;
        background-color: $header-color;
        img {
            width: 4rem;
        }
    }
</style>