<script setup lang="ts">

const technologies = [
  { name: 'React', description: 'Desarrollo rápido y modular de interfaces con React.' },
  { name: 'Tailwind CSS', description: 'Estilos rápidos y eficientes con Tailwind.' },
  { name: 'Redux', description: 'Manejo eficiente del estado global en aplicaciones con Redux.' },
  { name: 'Vue 3', description: 'Experto en desarrollo con Vue 3 para aplicaciones modernas.' },
  { name: 'Styled Components', description: 'Estilos en componentes reutilizables y dinámicos con Styled Components.' },
  { name: 'Strapi', description: 'API y CMS personalizables con Strapi para gestionar contenido.' },
  { name: 'JavaScript', description: 'Programación dinámica y flexible con JavaScript.' },
  { name: 'StoryBook', description: 'Desarrollo y prueba de componentes UI de manera aislada.' },
  { name: 'MobX', description: 'Flujo de datos reactivo para aplicaciones con MobX.' },
  { name: 'TypeScript', description: 'Desarrollo de aplicaciones más robustas con TypeScript.' },
  { name: 'Next.js', description: 'Framework para aplicaciones web optimizadas con React y SSR.' },
  { name: 'Formik', description: 'Facilitación de formularios manejables y validaciones con Formik.' }
]
</script>


<template>
  <div>
    <h2 class="text-4xl text-center mb-8 font-bold text-blue-500">Tecnologías</h2>
    <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-8">
      <div 
        v-for="tech in technologies" 
        :key="tech.name" 
        class="tech-card shadow-lg p-6 rounded-lg transition-transform transform hover:scale-105"
      >
        <h3 class="text-2xl font-bold">{{ tech.name }}</h3>
        <p>{{ tech.description }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.tech-card {
  transition: transform 0.3s ease; /* Suaviza el efecto */
}
</style>




