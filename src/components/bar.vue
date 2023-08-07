<template lang="pug">
div
  Bar(
    id="my-chart-id"
    :options="chartOptions"
    :data="chartData"
  )
</template>
<script>
import { defineComponent } from 'vue'
import { Bar } from 'vue-chartjs'
// eslint-disable-next-line
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale, Colors} from 'chart.js'
ChartJS.register(Title, Tooltip, Colors, Legend, BarElement, CategoryScale, LinearScale)

export default defineComponent({
  name: 'ComponentBar',
  components: {
    Bar
  },
  data () {
    return {
      chartData: {
        labels: ['Januaryfff', 'February', 'March', 'maio'],
        datasets: [{
          data: [40, 20, 12, 50],
          borderColor: '#7C8CF8',
          backgroundColor: '#7C8CF8',
          label: 'Data One'
        },
        {
          data: [40, 20, 12, 50],
          borderColor: '#7C8CF8',
          backgroundColor: '#',
          label: 'Data One'
        }]
      },
      chartOptions: {
        responsive: true
      }
    }
  }
})
</script>
