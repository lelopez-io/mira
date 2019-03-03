<template>
  <div id="slider">
    <button class="arrow left">
      <svg
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 129 129"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        enable-background="new 0 0 129 129"
      >
        <g>
          <path
            d="m88.6,121.3c0.8,0.8 1.8,1.2 2.9,1.2s2.1-0.4 2.9-1.2c1.6-1.6 1.6-4.2 0-5.8l-51-51 51-51c1.6-1.6 1.6-4.2 0-5.8s-4.2-1.6-5.8,0l-54,53.9c-1.6,1.6-1.6,4.2 0,5.8l54,53.9z"
          />
        </g>
      </svg>
    </button>

    <div class="collection">
      <div
        v-for="title in collection"
        :key="title.id"
        class="title"
        @click="$emit('select-title', title.id)"
      >
        <img
          :class="{ active: title.id == selected }"
          class="cover"
          src="https://image.tmdb.org/t/p/w500//xRWht48C2V8XNfzvPehyClOvDni.jpg"
        />
        <div v-if="title.id == selected" class="arrow-down"></div>
      </div>
    </div>

    <button class="arrow right">
      <svg
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 129 129"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        enable-background="new 0 0 129 129"
      >
        <g>
          <path
            d="m40.4,121.3c-0.8,0.8-1.8,1.2-2.9,1.2s-2.1-0.4-2.9-1.2c-1.6-1.6-1.6-4.2 0-5.8l51-51-51-51c-1.6-1.6-1.6-4.2 0-5.8 1.6-1.6 4.2-1.6 5.8,0l53.9,53.9c1.6,1.6 1.6,4.2 0,5.8l-53.9,53.9z"
          />
        </g>
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  props: ['collection', 'selected'],
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
$arrow-padding: 10px;

#slider {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #fff;
  position: relative;
  overflow: visable;
  padding-bottom: 30px;
}

.arrow {
  border: none;
  margin: 0;
  background: none;
  cursor: pointer;
  transition: background 250ms ease-in-out, transform 150ms ease;
  -webkit-appearance: none;
  -moz-appearance: none;

  &:hover {
    background: rgba(255, 255, 255, 0.1);
  }

  &:focus {
    outline: none;
  }

  &:active {
    transform: scale(1.2);
  }

  fill: #fff;
  border: none;

  & svg {
    height: 70px;
    width: 30px;
  }

  &.left {
    padding-left: $arrow-padding;
  }
  &.right {
    padding-right: $arrow-padding;
  }
}

.collection {
  margin-top: -30px;
  display: flex;
  justify-content: space-between;
}

.title {
  cursor: pointer;
}
.title img {
  max-height: 250px;
  margin: 0px 20px;
  border: 2px solid transparent;
  &:hover,
  &.active {
    border: 2px solid #fff;
  }
}

.arrow-down {
  width: 0;
  height: 0;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  border-top: 10px solid #fff;
  margin: -10px auto 0;
}
</style>
