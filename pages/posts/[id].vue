<script setup lang="ts">
import type { Post } from '~/interface/post.type';



const {id} = useRoute().params

const { data: post } = await useFetch<Post>(`https://rickandmortyapi.com/api/character/${id}`)

</script>

<template>
    <h1>post page: {{id}}</h1>
    <h3>{{ post?.name }}</h3>
    <p>{{ post?.status }}</p>
    <img :src="post?.image" alt="Character image" />
</template>