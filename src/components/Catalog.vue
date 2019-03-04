<template>
  <div id="catalog">
    <Collection
      :collection="titles"
      :selected="selected"
      v-on:select-title="selectTitle"
      v-on:hide-selection="selected = undefined"
    />
    <div v-if="selected !== undefined">
      <TitleInfo
        :selection="
          titles.find(title => {
            return title.id === selected
          })
        "
        :friendsList="friendsList"
      />
    </div>
  </div>
</template>

<script>
import Collection from '@/components/Collection.vue'
import TitleInfo from '@/components/TitleInfo'
import axios from 'axios'
export default {
  components: { Collection, TitleInfo },
  data() {
    return {
      titles: [],
      selected: undefined,
      friendsList: [
        {
          id: 1,
          name: 'luis',
          percentWatched: 33,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 2,
          name: 'enrrique',
          percentWatched: 53,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 3,
          name: 'lopez',
          percentWatched: 93,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 4,
          name: 'leon',
          percentWatched: 100,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 5,
          name: 'lelopez',
          percentWatched: 13,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 6,
          name: 'enrrique',
          percentWatched: 53,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 7,
          name: 'lopez',
          percentWatched: 93,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 8,
          name: 'leon',
          percentWatched: 100,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        },
        {
          id: 9,
          name: 'lelopez',
          percentWatched: 13,
          img:
            'https://pbs.twimg.com/profile_images/1072569190924607489/kUIUy96j_400x400.jpg'
        }
      ]
    }
  },
  methods: {
    selectTitle(id) {
      this.selected = id
      var element = document.getElementById('title-info')
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'end' })
      }
      //get list of friends watching this selected title and sort by highest
    }
  },
  created() {
    axios
      .get('https://2c32y722r7.execute-api.us-east-1.amazonaws.com/dev/Mira')
      .then(response => (this.titles = response))
  }
}
</script>

<style lang="scss" scoped>
#catalog {
  color: #fff;
  background-image: linear-gradient(transparent 5px, #141414 5px);

  min-height: 25vh;
}
</style>
