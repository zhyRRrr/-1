<script setup>
import {ref,reactive, onMounted} from 'vue'
import * as echarts from 'echarts';

const chart = ref();
onMounted(()=>{
     chartInit()
})
function chartInit(){
     // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(chart.value);

      // 指定图表的配置项和数据
      var option = {
        tooltip:{},
        series:[
            {
                type:'pie',
                roseType:'area',
                radius:[20,80],
                data:[
                    {value: 50,name:'除雪'},
                    {value: 38,name:'路基'},
                    {value: 32,name:'交安设施'},
                    {value: 30,name:'桥通'},
                    {value: 20,name:'绿化'},
                    {value: 26,name:'交通事故'},
                    {value: 18,name:'日常养护'},
                ],
                label:{
                    show:true,
                    formatter:'{b} {c}%',
                    textStyle:{
                        color:"#fff"
                    }
                }
            }
        ]
      };

      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
}
</script>

<template>
    
     <div ref="chart" style="width:100%;height:230px;"></div>
</template>

<style scoped>

</style>
