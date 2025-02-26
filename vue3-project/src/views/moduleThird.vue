<script setup>
import {ref,reactive} from 'vue'
import Waterpond from './chart/waterpond.vue'
import Rosechart from './chart/rosechart.vue'
import Map from './chart/map.vue'
</script>

<template>
    <div class="modulethird">
        <div class="modulethird-left">
            <Map/>
        </div>
        <div class="modulethird-right">
            <div class="bgstyle">
                <Waterpond />
                <dv-decoration-2 style="width:100%;height:5px;" />
                <Rosechart />
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
