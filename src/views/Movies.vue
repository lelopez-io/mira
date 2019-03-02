<template>
  <div id="movies">
    <Featured />
  </div>
</template>

<script>
// @ is an alias to /src
import Featured from '@/components/layout/Featured.vue'

export default {
  name: 'movies',
  components: {
    Featured
  }
}
</script>
