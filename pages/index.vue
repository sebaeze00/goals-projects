<script setup lang="ts">
useSeoMeta({
    title: 'Home Page',
    description: 'home page',
})




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
    <!-- <div>
        <h1>hola</h1>
        <UiButton/>
    </div> -->


 <section class="bg-blue-500 text-white py-16">
  <div class="container mx-auto text-center">
    <h1 class="text-5xl font-bold">¡Hola! Soy Sebastián Avila</h1>
    <p class="mt-4 text-xl">Desarrollador web apasionado por crear aplicaciones dinámicas y eficientes.</p>
  </div>
</section>


<section class="bg-white py-16">
    <h2 class="text-4xl text-center mb-8">Tecnologías</h2>
    <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-8">
        
      <div 
        v-for="tech in technologies" 
        :key="tech.name" 
        class="shadow-lg p-6 rounded-lg"
      >
        <h3 class="text-2xl font-bold">{{ tech.name }}</h3>
        <p>{{ tech.description }}</p>
      </div>
    </div>
  </section>

<section class="bg-gray-100 py-16">
  <div class="container mx-auto">
    <h2 class="text-4xl text-center mb-8">Proyectos Destacados</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div class="shadow-lg rounded-lg overflow-hidden">
        <!-- <img src="" alt="Proyecto 1"> -->
        <div class="p-4">
          <h3 class="text-xl font-bold">GEPP</h3>
          <p>GEPP es la única empresa de bebidas que cuenta con operación, fabricación, distribución y comercialización de bebidas carbonatadas y no carbonatadas, así como garrafones de agua en todo México.</p>
        </div>
        
      </div>
      <div class="shadow-lg rounded-lg overflow-hidden">
        <!-- <img src="" alt="Proyecto 1"> -->
        <div class="p-4">
          <h3 class="text-xl font-bold">Prisma</h3>
          <p>Prisma Medios de Pago es una reconocida empresa de servicios financieros y tecnología de pagos en Latinoamérica. Cuenta con el sistema LIQUOR, una plataforma integral y segura para procesar transacciones de pagos electrónicos del Banco Galicia Rural.</p>
        </div>
      </div>

      <div class="shadow-lg rounded-lg overflow-hidden">
        <!-- <img src="" alt="Proyecto 1"> -->
        <div class="p-4">
          <h3 class="text-xl font-bold">Language-lab</h3>
          <p>Language-Lab es un proyecto interno de Valtech donde se creó una página fácil de usar para que un docente pueda realizar pruebas y conocer qué nivel de inglés tiene el candidato.</p>
        </div>
      </div>

      <div class="shadow-lg rounded-lg overflow-hidden">
        <!-- <img src="" alt="Proyecto 1"> -->
        <div class="p-4">
          <h3 class="text-xl font-bold">Omint</h3>
          <p>Omint Venta Digital es una plataforma en línea que facilita la venta de planes de salud de la obra social Omint, permitiendo a los usuarios comparar opciones y gestionar su afiliación de manera sencilla y eficiente.</p>
        </div>
      </div>
    </div>
  </div>
</section>



<section class="bg-white py-16">
  <div class="container mx-auto">
    <div class="shadow-lg p-8 rounded-lg bg-gray-100 flex flex-col md:flex-row items-center">
      <div class="md:w-1/3 mb-8 md:mb-0">
        <img 
          src="../assets/foto-perfil.jpeg" 
          alt="Tu nombre" 
          class="rounded-full w-48 h-48 mx-auto shadow-lg" 
        />
      </div>
      <div class="md:w-2/3 md:ml-8 text-center md:text-left">
        <h2 class="text-3xl font-bold mb-4">Sobre mí</h2>
        <p class="text-lg mb-4">
          Soy un desarrollador Front-end de 22 años. Comencé mi carrera en 2022 en <strong>Arbusta</strong>, 
          donde me capacitaron y fui trainee. Trabajé allí por un año, donde adquirí mis primeras 
          habilidades en desarrollo. Actualmente trabajo en <strong>Valtech</strong>, donde llevo un año y 
          medio. Durante este tiempo he ascendido a desarrollador junior y participé en 4 proyectos clave que 
          me han permitido aprender diversas tecnologías y nutrirme de la experiencia de mis compañeros.
        </p>
      
        <p class="mb-4">Puedes enviarme un correo a: <span class="font-semibold">sebaeze00@gmail.com</span></p>
        <p class="mb-4">O llámame al: <span class="font-semibold">1161008485</span></p>
      </div>
    </div>
  </div>
</section>




<section class="bg-blue-500 text-white py-16">
  <div class="container mx-auto text-center">
    <h2 class="text-4xl mb-8">Contáctame</h2>
    <a href="mailto:sebaeze00@gmail.com" class="bg-white text-blue-500 px-4 py-2 rounded-lg">Envíame un correo</a>
  </div>
</section>

</template>