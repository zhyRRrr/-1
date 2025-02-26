<script setup>
import {ref,reactive} from 'vue'
const config = ref({
     data: [55],
    shape: 'round',
})

</script>

<template>
    <div class="waterpond-title">计划资金累计完成情况</div>
    <div class="waterpond-detail">
        累计完成<span>544362</span>元
    </div>
    <div class="waterpond">
    <dv-water-level-pond :config="config" style="width:200px;height:200px" />
    </div>
</template>

<style scoped>

</style>