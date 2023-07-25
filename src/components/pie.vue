<template lang="pug">
div
  Pie(
    id="my-chart-id"
    :options="chartOptions"
    :data="chartData"
  )
</template>
<script>
import { defineComponent } from 'vue'
import { Pie } from 'vue-chartjs'
// eslint-disable-next-line
import { Chart as ChartJS, ArcElement, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale, Colors} from 'chart.js'
ChartJS.register(ArcElement, Title, Tooltip, Colors, Legend, BarElement, CategoryScale, LinearScale)

export default defineComponent({
  name: 'ComponentPie',
  components: {
    Pie
  },
  data () {
    return {
      chartData: {
        labels: ['Red', 'Blue', 'Yellow'],
        datasets: [{ data: [300, 50, 100] }],
        borderColor: '#36A2EB',
        backgroundColor: [
          'rgb(255, 99, 132)',
          'rgb(54, 162, 235)',
          'rgb(255, 205, 86)'
        ]
      },
      chartOptions: {
        responsive: true
      }
    }
  }
})
</script>
