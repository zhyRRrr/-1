<script setup>
import {ref,reactive, onMounted} from 'vue'
import ModuleTitle from './moduleTitle.vue'
import ModuleFirst from './moduleFirst.vue'
import ModuleSecond from './moduleSecond.vue'
import ModuleThird from './moduleThird.vue'
import ModuleFourth from './moduleFourth.vue'

let screen = ref();
const getScale = (width=1920,height=1080)=>{
    let ww = window.innerWidth / width
    let wh = window.innerHeight / height
    return ww  < wh ? ww  : wh
}
onMounted(()=>{
   screen.value.style.transform = `scale(${getScale()}) translate(-50%,-50%)`
})
window.onresize=()=>{
    screen.value.style.transform = `scale(${getScale()}) translate(-50%,-50%)`
}
</script>

<template>
<div class="container" ref="screen">
<!-- 头部  -->
    <ModuleTitle />
    <!-- 主体部分  -->
    <div class="main">
        <ModuleFirst />
        <ModuleSecond />
        <ModuleThird />
        <ModuleFourth />
    </div>
</div>
</template>

<style scoped>
.container {
    position: fixed;
    width: 1920px;
    height: 1080px;
    left:50%;
    top:50%;
    transform-origin: left top;
}
</style>
