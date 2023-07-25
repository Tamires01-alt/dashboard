<template lang="pug">
div(
  class = "q-pa-md row items-start q-gutter-md"
  )
  q-card(
    class = "my-card"
    )
    q-card-section
      p(
         class="number"
      ) 1500
        q-icon(
          name="fa-solid fa-chart-line" size="20px" style="margin-left: 1em;"
        )
        p(
          class="text"
        )  Pessoas
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
<style lang="scss">

.number{
  font-size:35px;
  text-align: center
}
.text{
  font-size:15px;
  text-align: center;
  margin-top: -6px;
}
.my-card{
  width:250px;
  height:100px;
  background-color:#9512c9;
}
</style>
