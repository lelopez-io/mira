<template>
  <div class="home">
    <Featured />
  </div>
</template>

<script>
// @ is an alias to /src
import Featured from '@/components/layout/Featured.vue'

export default {
  name: 'home',
  components: {
    Featured
  }
}
</script>
