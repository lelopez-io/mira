<template>
  <div class="home">
    <Featured />
    <Catalog />
  </div>
</template>

<script>
// @ is an alias to /src
import Featured from '@/components/layout/Featured.vue'
import Catalog from '@/components/Catalog.vue'

export default {
  name: 'home',
  components: {
    Featured,
    Catalog
  }
}
</script>
