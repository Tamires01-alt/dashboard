<template lang="pug">
div
  Bubble(
    id="my-chart-id"
    :options="chartOptions"
    :data="chartData"
  )
</template>
<script>
import { defineComponent } from 'vue'
import { Bubble } from 'vue-chartjs'
// eslint-disable-next-line
import { Chart as ChartJS, ArcElement, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale, Colors, PointElement} from 'chart.js'
ChartJS.register(ArcElement, Title, Tooltip, Colors, Legend, BarElement, CategoryScale, LinearScale, PointElement)

export default defineComponent({
  name: 'ComponenteLine',
  components: {
    Bubble
  },
  data () {
    return {
      chartData: {
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [
              {
                x: 20,
                y: 25,
                r: 5
              },
              {
                x: 40,
                y: 10,
                r: 10
              },
              {
                x: 30,
                y: 22,
                r: 30
              }
            ]
          },
          {
            label: 'Data Two',
            backgroundColor: '#7C8CF8',
            data: [
              {
                x: 10,
                y: 30,
                r: 15
              },
              {
                x: 20,
                y: 20,
                r: 10
              },
              {
                x: 15,
                y: 8,
                r: 30
              }
            ]
          }
        ]
      },
      chartOptions: {
        responsive: true
      }
    }
  }
})
</script>
