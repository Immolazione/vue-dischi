<template>
<div>
  <Header />
  <Main />
</div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
export default {
  name: 'App',
  Header,
  Main
}
</script>

<style lang="scss">
@import './assets/scss/_generics.scss';
@import './assets/scss/_utils.scss';
@import './assets/scss/_vars.scss';
</style>
