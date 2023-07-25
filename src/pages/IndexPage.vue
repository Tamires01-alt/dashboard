<template lang="pug">
div
  div.row.justify-center.items-start.content-start
    card
    card
    card
    card
  div
    bar
  div
    pie
  div
    bubble
</template>

<script>
import { defineComponent } from 'vue'
import card from 'components/card.vue'
import bar from 'components/bar.vue'
import pie from 'components/pie.vue'
import bubble from 'components/bubble.vue'
import axios from 'axios'

export default defineComponent({
  name: 'IndexPage',
  components: {
    card,
    bar,
    pie,
    bubble
  },
  async created () {
    const { data } = await axios.get('https://dummyjson.com/products')
    console.log(data)
  }
})
</script>
