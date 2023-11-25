<template>
    <div class="card">
        <img :src="`/images/${props.experience.image}`">
        <span class="card__text">{{ props.experience.name }}</span>
    </div>
</template>

<script setup lang="ts">
const props = defineProps(['experience'])
</script>

<style>
</style>