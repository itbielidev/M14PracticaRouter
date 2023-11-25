<script setup lang="ts">
import data from '@/assets/data.json'

</script>
<template>
    <div>
        <nav>
            <RouterLink to="/">
                <h2>Home</h2>
            </RouterLink>
            <RouterLink v-for="location in data.destinations" :key="location.id" :to="`/destination/${location.id}/${location.slug}`">
                <p>{{ location.name }}</p>
            </RouterLink>
            <a href="https:www.itb.cat">ITB</a>
        </nav>
    </div>
</template>