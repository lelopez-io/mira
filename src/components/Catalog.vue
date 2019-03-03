<template>
  <div id="catalog">
    <Collection />
  </div>
</template>

<script>
import Collection from '@/components/Collection.vue'
export default {
  components: { Collection }
}
</script>

<style lang="scss" scoped>
#catalog {
  color: #fff;
  background-image: linear-gradient(transparent 5px, #141414 5px);

  min-height: 25vh;
}
</style>
