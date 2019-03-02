<template>
  <div id="nav">
    <router-link to="/" class="logo">MIRA</router-link>
    <ul class="nav-links">
      <router-link to="/">Home</router-link>
      <!-- <router-link to="/tvshows">TV Shows</router-link> -->
      <router-link to="/movies">Movies</router-link>
      <router-link to="/about">About</router-link>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
#nav {
  padding: 30px;
  background: #141414;
  display: flex;

  a {
    text-decoration: none;
  }

  & .logo,
  & .logo.router-link-exact-active {
    color: #e50914;
    font-weight: bold;
    font-size: 25px;
  }

  .nav-links {
    margin: 0;
    padding: 0;
    display: flex;
    align-items: center;
    & a {
      margin-left: 20px;

      color: #b3b3b3;
      &.router-link-exact-active {
        color: #fff;
      }
    }
  }
}
</style>
