<template>
  <div id="social">
    <h3>21 friends have watched this</h3>
    <div class="friends">
      <div class="chart" v-for="friend in friendsList" :key="friend.id">
        <svg viewBox="0 0 36 36" class="circular-chart">
          <path
            class="circle-bg"
            d="M18 2.0845
          a 15.9155 15.9155 0 0 1 0 31.831
          a 15.9155 15.9155 0 0 1 0 -31.831"
          />
          <path
            class="circle"
            :stroke-dasharray="calcPercent(friend.percentWatched)"
            d="M18 2.0845 a 15.9155 15.9155 0 0 1 0 31.831 a 15.9155 15.9155 0
          0 1 0 -31.831"
          />
          <defs>
            <clipPath id="circleView">
              <circle cx="18" cy="18" r="15" fill="#FFFFFF" />
            </clipPath>
          </defs>
          <image
            width="35"
            height="35"
            :href="friend.img"
            :title="friend.name"
            clip-path="url(#circleView)"
          />
        </svg>
        <div class="overlay">{{ friend.name }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['friendsList'],
  methods: {
    calcPercent(value) {
      return value + ', 100'
    }
  }
}
</script>

<style lang="scss" scoped>
#social {
  padding-left: 60px;
  min-width: calc((100vw - 240px) / 2);
  text-align: center;
}

.friends {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.chart {
  width: 20%;
  max-width: 75px;
  min-width: 50px;

  & p {
    text-align: center;
  }
}

.circular-chart {
  display: block;
  margin: 10px auto;
  max-width: 80%;
  max-height: 250px;
}

.circle-bg {
  fill: none;
  stroke: #eee;
  stroke-width: 2;
}

.circle {
  fill: none;
  stroke-width: 2;
  stroke-linecap: round;
  animation: progress 1s ease-out forwards;
}

@keyframes progress {
  0% {
    stroke-dasharray: 0 100;
  }
}

.circular-chart .circle {
  stroke: #e50914;
}

.percentage {
  fill: #666;
  font-family: sans-serif;
  font-size: 0.5em;
  text-anchor: middle;
}

.overlay {
  font-size: 0.75rem;
  max-width: 100%;
}
</style>
