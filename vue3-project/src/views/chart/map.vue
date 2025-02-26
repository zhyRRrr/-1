<script setup>
import {ref,reactive, onMounted} from 'vue'
import * as echarts from 'echarts';
import chinaMap from '../../assets/json/china.json'

let chart =ref();
onMounted(()=>{
    chartInit()
})
function chartInit(){
     // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(chart.value);
      echarts.registerMap('china',chinaMap)

      // 指定图表的配置项和数据
      var option = {
            geo:{
                type:'map',
                map:'china',
                label:{
                    show:true,
                    color:'#fff',
                    fontSize:10
                },
                itemStyle:{
                    areaColor:'#4D98FB',
                    borderColor:'#fff'
                },
                zoom:1.2,
                emphasis:{
                        lable:{
                            color:'#333'
                        },
                        itemStyle:{
                            areaColor:"#1BC1AD"
                        }
                    }
            },
            series:[
                {
                    type: 'effectScatter',
                    coordinateSystem: 'geo',
                    label: {
                        formatter: '{b}',
                        position: 'right',
                        show: true
                    },
                    itemStyle: {
                        shadowBlur: 10,
                        shadowColor: '#f00',
                        color:'#f00'
                    },
                    symbolSize:20,
                     rippleEffect: {
                        brushType: 'stroke',
                        scale:3
                    },
                    data:[
                        {name:'北京',value: [116.46, 39.92]},
                        {name:'乌鲁木齐',value: [87.68, 43.77]},
                        {name:'海口',value:  [110.35, 20.02]},
                        {name:'大连',value: [121.62, 38.92]}
                        ],
                },
                //箭头动画
                {
                    type:"lines",
                    effect:{
                        show:true,
                        period:5,
                        shmbol:'arrow',
                        symbolSize:10
                    },
                    lineStyle:{
                        color:'#C1A43C',
                        width:1,
                        opacity:1,
                        curveness:0.1,
                    },
                    data:[
                        [
                            {coord: [91.11, 29.97],},
                            {coord:[121.48, 31.22]}
                        ],
                        [
                            {coord:  [110.35, 20.02]},
                            {coord: [121.62, 38.92]}
                        ]
                    ]
                }
            ]
      };

      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
}
</script>

<template>
  <div ref="chart" style="width: 100%;height:600px;"></div>
</template>

<style scoped>

</style>
