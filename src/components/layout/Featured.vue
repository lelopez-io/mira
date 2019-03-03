<template>
  <div id="featured">
    <video
      class="video"
      playsinline=""
      autoplay=""
      muted=""
      loop=""
      src="https://app.coverr.co/s3/mp4/Magic-Mouse-Scroll.mp4"
      poster="https://storage.googleapis.com/coverr-public/poster/Magic-Mouse-Scroll.jpg"
    ></video>

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
#featured {
  box-shadow: inset 0px 0px 200px 100px rgba(0, 0, 0, 0.8);

  z-index: -1;
  width: 100%;
  height: calc(95vh - 100px);
  margin-bottom: -75px;
}
.selection {
  color: #fff;
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

.video {
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translateX(-50%) translateY(-50%);
  transform: translateX(-50%) translateY(-50%);
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  z-index: -1000;
  overflow: hidden;
}

.selection {
  position: absolute;
  top: 100px;
  left: 0;
}
</style>
