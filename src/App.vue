<script setup lang="ts">
import { RouterView } from 'vue-router'
import TheNavigation from './components/TheNavigation.vue'

</script>
<template>
  <header>
    <TheNavigation></TheNavigation>
  </header>
  <div class="conainer">
    <RouterView/>
  </div>
</template>

<style scoped>
*{
  font-family: Arial, Helvetica, sans-serif;
  margin: 0;
  padding: 0;
}
</style>