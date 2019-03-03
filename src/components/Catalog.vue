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
export default {
  components: { Collection, TitleInfo },
  data() {
    return {
      titles: [
        {
          id: 1,
          title: 'Altina: Battle Angel',
          category: 'Fantasy/Science Fiction',
          description:
            'When Alita awakens with no memory of who she is in a future world she does not recognize, she is taken in by Ido, a compassionate doctor who realizes that somewhere in this abandoned cyborg shell is the heart and soul of a young woman with an extraordinary past.',
          runtime: 122,
          year: 2019,
          price: 25.99,
          img:
            'https://image.tmdb.org/t/p/w500//xRWht48C2V8XNfzvPehyClOvDni.jpg'
        },
        {
          id: 2,
          title: 'Glass',
          category: 'Drama/Fantasy',
          description:
            'When Alita awakens with no memory of who she is in a future world she does not recognize, she is taken in by Ido, a compassionate doctor who realizes that somewhere in this abandoned cyborg shell is the heart and soul of a young woman with an extraordinary past.',
          runtime: 129,
          year: 2019,
          price: 25.99,
          img:
            'https://image.tmdb.org/t/p/w500//svIDTNUoajS8dLEo7EosxvyAsgJ.jpg'
        },
        {
          id: 3,
          title: 'Spider Man',
          category: 'Fantasy/Science Fiction',
          description:
            'When Alita awakens with no memory of who she is in a future world she does not recognize, she is taken in by Ido, a compassionate doctor who realizes that somewhere in this abandoned cyborg shell is the heart and soul of a young woman with an extraordinary past.',
          runtime: 135,
          year: 2018,
          price: 19.99,
          img:
            'https://image.tmdb.org/t/p/w500//iiZZdoQBEYBv6id8su7ImL0oCbD.jpg'
        },
        {
          id: 4,
          title: 'How to Train',
          category: 'Fantasy/Science Fiction',
          description:
            'When Alita awakens with no memory of who she is in a future world she does not recognize, she is taken in by Ido, a compassionate doctor who realizes that somewhere in this abandoned cyborg shell is the heart and soul of a young woman with an extraordinary past.',
          runtime: 135,
          year: 2018,
          price: 19.99,
          img:
            'https://image.tmdb.org/t/p/w500//xvx4Yhf0DVH8G4LzNISpMfFBDy2.jpg'
        }
      ],
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
