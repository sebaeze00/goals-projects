<script setup lang="ts">

interface CardMainProps{
    name:string;
    status:string;
    id:number;
    url:string,
}

const {name, status, id, url} = defineProps<CardMainProps>();

</script>

<template >
    <div class="p-4">
        <h2 class="font-bold"">{{ id }} - {{ name }}</h2>
        <img :src="url" :alt="name">
        <p>{{ status }}</p>   
        <NuxtLink :to="`/posts/${id}`">Read more</NuxtLink>
    </div>
</template>