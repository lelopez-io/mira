<template>
  <div id="featured">
    <div class="selection" v-if="selection !== ''">
      <h1>{{ selection }}</h1>
      <select>
        <option v-for="genre in genres" :key="genre">
          {{ genre | titleCase }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selection: '',
      pathis: {
        '': '',
        tvshows: 'TV Shows',
        movies: 'Movies'
      },
      genres: [
        'action',
        'adventure',
        'animation',
        'comedy',
        'crime',
        'documentary',
        'drama',
        'family',
        'fantasy',
        'history',
        'horror',
        'music',
        'mystery',
        'romance',
        'science fiction',
        'thriller',
        'war',
        'western'
      ]
    }
  },
  created() {
    this.selection = this.pathis[this.$route.path.substring(1)]
  },
  filters: {
    titleCase: function(str) {
      return str.replace(/\w\S*/g, function(txt) {
        return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase()
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.selection {
  padding: 30px;
  display: flex;
  align-items: center;

  & select {
    -webkit-appearance: none;
    border-radius: 0;
    border: 1px solid;
    padding-left: 10px;
    margin-left: 20px;
    color: #fff;
    background-color: #000;

    line-height: 2rem;
    font-size: 0.9rem;
  }
}
</style>
