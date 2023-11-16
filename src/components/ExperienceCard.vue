<template>
    <div>
        <img src="" alt="">
        <span>Top Experience</span>
    </div>
</template>

<script setup lang="ts">
import Data from '@/assets/data.json'
import {reactive} from 'vue';
const location = reactive(Data.destinations)
</script>

<style>
</style>