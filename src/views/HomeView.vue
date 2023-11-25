<script setup lang="ts">
import data from '@/assets/data.json'
</script>

<template>
  <main class="home">
    <h1>All destinations</h1>

    <div class="destinations">
      <RouterLink v-for="location in data.destinations" :key="location.id" :to="`/destination/${location.id}/${location.slug}`">
      <section class="destinations-box">
        <article class="destination-box">
          <h2>{{ location.name }}</h2>
          <img class="destination-cover" :src="`/images/${location.image}`" :alt="location.name">
        </article>

      </section>
    </RouterLink>
    </div>
  </main>
</template>

<style scoped>

h1,h2{
  font-weight: bold;
}



</style>
