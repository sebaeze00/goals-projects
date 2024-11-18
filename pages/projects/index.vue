<script setup lang="ts">
import { ref, computed } from 'vue';

interface Post {
  id: number;
  name: string;
  status: string;
  species: string;
  gender: string;
  origin: {
    name: string;
  };
  image: string;
}

const { data } = await useFetch<{ results: Post[] }>("https://rickandmortyapi.com/api/character");
const posts = ref(data.value?.results || []);

const searchQuery = ref<string>('');


// EL METODO COMPUTADO REEVALUA CONSTANTEMENTE LOS CAMBIOS DE LA CONSTANTE 
const filteredPosts = computed(() =>
  posts.value.filter((post) =>
    post.name.toLowerCase().includes(searchQuery.value.toLowerCase())
  )
);
</script>

<template>
  <h2 class="pt-10 text-4xl text-center mb-8 font-bold text-purple-500">Componente para proyectos.</h2>

  <div class="flex flex-col items-center">

    <!-- BUSCADOR -->
    <input
      v-model="searchQuery"
      type="text"
      placeholder="Search by name..."
      class="mb-6 p-2 border border-gray-300 rounded-md w-80 focus:outline-none focus:ring-2 focus:ring-purple-600"
    />

    <!-- CARTAS -->

    <div class="flex flex-wrap justify-center gap-4">
      <CardMain
        v-for="{ id, name, status, image, species, gender, origin } of filteredPosts"
        :key="id"
        :name="name"
        :status="status"
        :id="id"
        :url="image"
        :species="species"
        :gender="gender"
        :origin="origin"
      />
    </div>

    <p v-if="filteredPosts.length === 0" class="text-gray-500 mt-6">No characters found</p>
  </div>
</template>