<script setup lang="ts">
useSeoMeta({
    title: 'Home Page',
    description: 'home page',
})
</script>

<template>
 <section class="bg-blue-500 text-white py-16">
  <div class="container mx-auto text-center">
    <h1 class="text-5xl font-bold">¡Hola! Soy Sebastián Avila</h1>
    <p class="mt-4 text-xl">Desarrollador web apasionado por crear aplicaciones dinámicas y eficientes.</p>
  </div>
</section>

<section class="bg-white py-16">
  <Technologies />
</section>

<section class="bg-gray-100 py-16">
  <MyProjects/>
</section>

<section class="bg-white py-16">
  <AboutMe/>
</section>

<section class="bg-blue-500 text-white py-16">
    <div class="container mx-auto text-center">
      <h2 class="text-4xl mb-8">Contáctame</h2>
      <ContactModal />
    </div>
  </section>


</template>