<script setup>
</script>
<template>
    <div>
        <nav>
            <RouterLink to="/">
                <h2>Home</h2>
            </RouterLink>
            <RouterLink v-for="location in locations" :key="location.id" :to="{name:'destination', params:{id:location.id}}">
                <p>{{ location.name }}</p>
            </RouterLink>
            <a href="https:www.itb.cat">ITB</a>
        </nav>
    </div>
</template>