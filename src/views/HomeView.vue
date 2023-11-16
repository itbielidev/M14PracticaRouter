<script setup lang="ts">
import Data from '@/assets/data.json'
import { ref } from 'vue';
import DestinationShow from './DestinationShow.vue';
const info=ref(Data.destinations)
</script>

<template>
  <main>
<h1>All destinations</h1>
<section class="destinations-box">
  <article class="destination-box">
    <h2>Title</h2>
    <img class="destination-cover" src="https://as01.epimg.net/diarioas/imagenes/2022/04/20/actualidad/1650466413_240889_1650466661_noticia_normal_recorte1.jpg" alt="" srcset="">
  </article>
  <article class="destination-box"></article>
  <article class="destination-box"></article>
  <article class="destination-box"></article>

</section>
  </main>

  <div class="home">
    <RouterLink v-for="destination in info" :key="destination.id" :to="{name:'destination.show', params:{id:destination.id}}" >
    <h2>{{ destination.name }}</h2>
      <img src="`/images/${destination.image}`" alt="destination.name">
    </RouterLink>
    <RouterView></RouterView>
  </div>
</template>

<style scoped>

h1,h2{
  font-weight: bold;
}

.destinations-box{
  display: flex;
}

.destination-cover{
  width: 200px;
  height: 125px;
}


</style>
