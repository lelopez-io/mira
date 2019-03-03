<template>
  <div id="catalog">
    <Collection
      :collection="titles"
      :selected="selected"
      v-on:select-title="selectTitle"
    />
    <div v-if="selected !== undefined">
      <TitleInfo
        :selection="
          titles.find(title => {
            return title.id === selected
          })
        "
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
          price: 25.99
        },
        {
          id: 2,
          title: 'Glass',
          category: 'Drama/Fantasy',
          description:
            'When Alita awakens with no memory of who she is in a future world she does not recognize, she is taken in by Ido, a compassionate doctor who realizes that somewhere in this abandoned cyborg shell is the heart and soul of a young woman with an extraordinary past.',
          runtime: 129,
          year: 2019,
          price: 25.99
        },
        {
          id: 3,
          title: 'Black Panther',
          category: 'Fantasy/Science Fiction',
          description:
            'When Alita awakens with no memory of who she is in a future world she does not recognize, she is taken in by Ido, a compassionate doctor who realizes that somewhere in this abandoned cyborg shell is the heart and soul of a young woman with an extraordinary past.',
          runtime: 135,
          year: 2018,
          price: 19.99
        }
      ],
      selected: undefined
    }
  },
  methods: {
    selectTitle(id) {
      this.selected = id
      var element = document.getElementById('title-info')
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'end' })
      }
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
