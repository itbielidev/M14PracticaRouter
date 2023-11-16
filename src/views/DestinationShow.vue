<script setup lang="ts">
import Data from '@/assets/data.json'
import type ExperienceCardVue from '@/components/ExperienceCard.vue';
import {reactive} from 'vue';
import {useRoute} from 'vue-router';
const locations = reactive(Data)

//acceder a los params de la url
const route = useRoute()
const locationId = <number><any> route.params.id

//buscar los datos de la ubicacion
</script>
<template>
    <main>
        <h1>{{ locations.destinations[locationId-1].name }}</h1>
        <p>{{ locations.destinations[locationId-1].description }}</p>
        <img :src="`/img/${locations.destinations[locationId-1].image}`">
        <section id="top-experiences">
            <h2>Top experiences in {{ locations.destinations[locationId-1].name }}</h2>
            <ExperienceCardVue experience></ExperienceCardVue>
            //Hare un router link con un v-for envolviendo esta experience card pasando un argumento por parametro
        </section>
    </main>
</template>