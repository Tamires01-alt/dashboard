<template lang="pug">
div(
  class="bg-slate-300"
)
  div.row.justify-center.items-start.content-start
    card
    card
    card
    card
  div(
    class="q-pa-md example-row-equal-width "
  )
    div(
      class="md:grid grid-cols-2 gap-10 md:ml-10"
    )
      div(
        class="bg-white"
      )
        bar
      div(
      )
        pie(
          class="md:w-96 md:h-96 bg-white"
        )
  div
    bubble(
      class="md:w-1/2 md:h-1/2 md:ml-10 bg-white"
    )
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
  data () {
    return {
      produto: false
    }
  },
  mounted () {
    axios
      .get('https://dummyjson.com/products')
      .then(response => (this.produto = response.data))
  }
})
</script>
