<script setup lang="ts">
import type { Post } from '~/interface/post.type';

const { data } = await useFetch<{ results: Post[] }>("https://rickandmortyapi.com/api/character");
const posts = data.value?.results || [];
</script>



<template>
    <div>
        <h1>post page</h1>

        <CardMain
        v-for="{id, name, status, image} of posts"
        :key="id"
        :name="name"
        :status="status"
        :id="id"
        :url="image"
        />

    </div>
</template>