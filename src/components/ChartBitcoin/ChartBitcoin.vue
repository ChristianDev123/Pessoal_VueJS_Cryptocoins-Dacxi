<template>
  <LineChartGenerator
    :chart-options="chartOptions"
    :chart-data="dataBitcoin"
  />
</template>

<script>
import { Line as LineChartGenerator } from 'vue-chartjs'

import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    LineElement,
    LinearScale,
    CategoryScale,
    PointElement,
} from 'chart.js'

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  LineElement,
  LinearScale,
  CategoryScale,
  PointElement
)

export default {
    name: 'LineChart',
    props:["dataBitcoin"],
    components: {
        LineChartGenerator
    },
    data() {
        return {
            chartOptions: {
                responsive: true,
                maintainAspectRatio: false, 
                labels:{
                    font:{fontColor:'#fff',}
                },
                scales:{
                    x:{
                        grid:{color:'rgba(0,0,0,0.5)'},
                        ticks:{color:'#216190'}
                    },
                    y:{
                        grid:{color:'rgba(0,0,0,0.5)'},
                        ticks:{color:'#216190'}
                    }
                }
            }
        }
    },
}
</script>
