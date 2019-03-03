<template>
  <div id="selection">
    <div id="title-info">
      <h2>{{ selection.title }}</h2>
      <p class="specs">
        <span>{{ selection.year }}</span>
        <span>{{ selection.rating }}</span>
        <span>{{ selection.runtime }}m</span>
      </p>
      <p class="description">{{ selection.description }}</p>
      <div class="title-options">
        <button class="btn play">PLAY</button>
        <button class="btn ">+ My List</button><br />

        <button class="btn circle"><span> 👍</span></button>
        <button class="btn circle"><span> 👎</span></button>
        <button class="btn circle" @click="showSocial = !showSocial">
          <span>21</span>
        </button>
      </div>

      <p class="additional">
        <span><strong>Genres:</strong> {{ selection.category }}</span
        ><br />
        <span><strong>Staring:</strong> {{ selection.category }}</span>
      </p>
    </div>
    <transition name="slide">
      <Social v-if="showSocial === true" :friendsList="friendsList" />
    </transition>
  </div>
</template>

<script>
import Social from '@/components/Social.vue'
export default {
  components: { Social },
  props: ['selection', 'friendsList'],
  data() {
    return {
      showSocial: false
    }
  },
  methods: {
    scrollDown() {}
  },
  mounted() {
    var element = document.getElementById('title-info')
    element.scrollIntoView({ behavior: 'smooth', block: 'end' })
  }
}
</script>

<style lang="scss" scoped>
#selection {
  padding: 30px 60px;
  display: flex;
  flex: 1 1 auto;
}
#title-info {
  padding-bottom: 70px;
}

.specs span {
  padding-right: 10px;
  font-weight: bold;
}

.btn {
  -webkit-appearance: none;
  cursor: pointer;
  border-radius: 0;
  border: 1px solid;
  padding: 0 20px;
  margin-right: 20px;
  color: #fff;
  background-color: #000;

  line-height: 2rem;
  font-size: 0.9rem;
  transition: background 250ms ease-in-out, transform 150ms ease;
  transition: transform 250ms ease-in-out, transform 150ms ease;

  &:hover {
    transform: scale(1.1);
    background: rgba(255, 255, 255, 0.1);
  }

  &.play {
    background-color: #e50914;
    border: 1px solid #e50914;
    margin-bottom: 10px;
    &:active,
    &:focus {
      border-color: #fff;
    }
  }

  &.circle {
    padding: 0px;
    margin: 20px 20px 0 0;
    height: 34px;
    width: 34px;
    border-radius: 55%;

    & span {
      text-align: center;
    }
    &:focus {
      outline: none;
    }
  }
}
/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-enter-active {
  transition: all 1.3s ease;
}
.slide-leave-active {
  transition: all 1.3s ease;
}
.slide-enter,
.slide-leave-to {
  transform: translateX(10px);
  opacity: 0;
}
</style>
