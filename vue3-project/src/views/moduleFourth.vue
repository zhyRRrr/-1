<script setup>
import {ref,reactive} from 'vue'
import Peichart from './chart/peichart.vue'

const list = ref([
    {value:55}, {value:46}, {value:37}, {value:62}, {value:58},
])
</script>

<template>
    <div class="modulefourth">
        <div class="modulefourth-list">
            <ul>
                <li class="bgstyle" v-for="(v,i) in list" :key="i">
                    <div class="peichart">
                        <h2>测试路段 </h2>
                        <Peichart :value="v.value" />
                    </div>
                    <dv-decoration-2 :reverse="true" style="width:5px;height:230px;" />
                </li>
                
            </ul>
        </div>
    </div>
</template>

<style scoped>

</style>
