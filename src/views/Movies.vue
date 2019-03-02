<template>
  <div id="movies">
    <Featured />
    <Catalog />
  </div>
</template>

<script>
// @ is an alias to /src
import Featured from '@/components/layout/Featured.vue'
import Catalog from '@/components/Catalog.vue'

export default {
  name: 'movies',
  components: {
    Featured,
    Catalog
  }
}
</script>
