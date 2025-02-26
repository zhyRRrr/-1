<script setup>
import {ref,reactive, onMounted} from 'vue'
import * as echarts from 'echarts';

let chart =ref();
onMounted(()=>{
    chartInit()
})
function chartInit(){
     // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(chart.value);

      // 指定图表的配置项和数据
      var option = {
        title: {   
          text: '巡查上报记录数量',
          textStyle:{
            color:'#fff',
            fontSize: 20
          }
        },
        tooltip: {},
        xAxis: {
          type:'value',
          axisLine:{
            lineStyle:{
                color:'#fff'
            }
          }
        },
        yAxis: {
            type:'category',
            data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子'],
            axisLine:{
            lineStyle:{
                color:'#fff'
            }
          }
        },
        series: [
          {
            name: '销量',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20],
            barWidth:40,
            itemStyle:{
                color:function(params){
                    var colorList = ['#ffdb5c','#fb7293','#67e0e3','#9d96f5','#8378ea','#e690d1']
                    return colorList[params.dataIndex]
                }
            }
          }
        ],
        toolbox:{ //工具箱  
            show:true,
            left:'right',
            feature:{
                saveAsImage:{},
                dataView:{},
                restore:{},
                magicType:{
                    type:['line','bar']
                }
            }
        },
        grid:{
            left:'2%',
            right:'2%',
            top:'10%',
            bottom:'2%',
            containLabel:true,
        }
      };

      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
}
</script>

<template>
  <div ref="chart" style="width: 100%;height:500px;"></div>
</template>

<style scoped>

</style>
