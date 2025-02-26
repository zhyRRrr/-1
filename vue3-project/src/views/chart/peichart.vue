<script setup>
import {ref,reactive,defineProps} from 'vue'
const {value} = defineProps({
    value:{
        type:Number
    }
})

const option = ref({
     series: [
    {
      type: 'gauge',
      startAngle: -Math.PI / 2,
      endAngle: Math.PI * 1.5,
      arcLineWidth: 15,
      data: [
        { name: 'itemA', value: value, gradient: ['#C1A43C', '#C1A43C', '#2fded6'] }
      ],
      axisLabel: {
        show: false
      },
      axisTick: {
        show: false
      },
      pointer: {
        show: false
      },
      dataItemStyle: {
        lineCap: 'round'
      },
      details: {
        show: true,
        formatter: '{value}%',
        style: {
            fill: '#1ed3e5',
            fontSize: 25
        }
      }
    }
  ]
})
</script>

<template>
   <dv-charts :option="option" style="width:100%;height:200px" />
</template>

<style scoped>

</style>
