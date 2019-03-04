<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from '@/components/layout/Header.vue'

export default {
  components: {
    Header
  }
}
</script>

<style lang="scss">
html,
body {
  margin: 0;

  max-width: 100% !important;
  overflow-x: hidden !important;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
