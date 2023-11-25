<script setup lang="ts">
import data from '@/assets/data.json'
import ExperienceCardVue from '@/components/ExperienceCard.vue';
import { ref, watch } from 'vue';
import {useRoute} from 'vue-router';

//acceder a los params de la url
const route = useRoute()
const locationId = ref(route.params.id as unknown as number)
const selectedExperience: any = ref(null)


watch(() => route.params, (newParams, _) => {
    locationId.value = newParams.id as unknown as number
})

//buscar los datos de la ubicacion
</script>
<template>
    <main>
        <h1>{{ data.destinations[locationId-1].name }}</h1>
        <button>GO BACK</button>
        <div class="destination-details">
            <img :src="`/images/${data.destinations[locationId-1].image}`">
            <p>{{ data.destinations[locationId-1].description }}</p>
        </div>
        <section class="experiences">
            <h2>Top experiences in {{ data.destinations[locationId-1].name }}</h2>
            <div class="cards">
                <button @click="() => selectedExperience = experience" v-for="experience in data.destinations[locationId-1].experiences" :key="experience.name">
                    <ExperienceCardVue :experience="experience"></ExperienceCardVue>
                </button>
            </div>
            
        </section>
        <section v-if="selectedExperience" class="experience-details">
            <h3>{{ selectedExperience.name }}</h3>
            <img :src="`/images/${selectedExperience.image}`">
            <p>{{ selectedExperience.description }}</p>
        </section>
    </main>
</template>

<style scoped>
main {
    padding: 1rem;
}
button {
    border: none;
    background: transparent;
    margin: 0;
    padding: 0;
    cursor: pointer;
}
</style>