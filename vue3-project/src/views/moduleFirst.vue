<script setup>
import {ref,reactive} from 'vue'

const modulefirstList = ref([
    {title:'管养里程',num:'3435',unit:'座'},
    {title:'桥梁',num:'234',unit:'个'},
    {title:'匝道',num:'678',unit:'个'},
    {title:'隧道',num:'985',unit:'个'},
    {title:'涵洞隧道',num:'443',unit:'个'},
    {title:'服务区',num:'343',unit:'个'},
    {title:'收费站',num:'76',unit:'个'},
    {title:'超限站',num:'45',unit:'个'},
    {title:'停车区',num:'24',unit:'个'},
])
</script>

<template>
    <div class="modulefirst">
        <ul>
            <li v-for="(v,i) in modulefirstList" :key="i">
                <div class="modulefirst-title">{{v.title}}</div>
                <div class="modulefirst-item">
                    <span class="modulefirst-num">{{v.num}}</span>
                    <span class="modulefirst-unit">{{v.unit}}</span>
                </div>
            </li>
            
        </ul>
    </div>
</template>

<style scoped>

</style>
