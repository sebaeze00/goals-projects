<script setup lang="ts">
import { ref } from 'vue'
import { 
  MailIcon, 
  PhoneIcon, 
  LinkedinIcon, 
  GithubIcon, 
} from 'lucide-vue-next'


interface ContactMethod {
  name: string;
  value: string;
  icon: any; 
  link: string;
}

const isOpen = ref(false)

const contactMethods: ContactMethod[] = [
  {
    name: 'Correo Electrónico',
    value: 'sebaeze00@gmail.com',
    icon: MailIcon,
    link: 'mailto:sebaeze00@gmail.com'
  },
  {
    name: 'Teléfono',
    value: '1161008485',
    icon: PhoneIcon,
    link: 'tel:1161008485'
  },
  {
    name: 'LinkedIn',
    value: 'Sebastian Avila',
    icon: LinkedinIcon,
    link: 'https://www.linkedin.com/in/sebastian-avila-4a881622b/'
  },
  {
    name: 'Github',
    value: 'sebaeze',
    icon: GithubIcon,
    link: 'https://github.com/sebaeze00'
  },
]

const openModal = () => {
  isOpen.value = true
}

const closeModal = () => {
  isOpen.value = false
}
</script>


<template>
  <div>
    <button 
      @click="openModal" 
      class="bg-white text-blue-500 px-4 py-2 rounded-lg hover:bg-blue-100 transition-colors"
    >
      Contáctame
    </button>

    <div 
      v-if="isOpen" 
      class="fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center"
      @click.self="closeModal"
    >
      <div 
        class="bg-white rounded-lg p-8 max-w-md w-full mx-4 transform transition-all"
        @click.stop
      >
        <h2 class="text-2xl font-bold mb-6 text-center text-blue-600">Medios de Contacto</h2>
        
        <div class="space-y-4">
          <a 
            v-for="method in contactMethods" 
            :key="method.name"
            :href="method.link"
            target="_blank"
            class="flex items-center p-4 bg-blue-50 rounded-lg hover:bg-blue-100 transition-colors"
          >
            <component 
              :is="method.icon" 
              class="w-6 h-6 mr-4 text-blue-500"
            />
            <div>
              <p class="font-semibold text-blue-800">{{ method.name }}</p>
              <p class="text-blue-600">{{ method.value }}</p>
            </div>
          </a>
        </div>

        <button 
          @click="closeModal" 
          class="mt-6 w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600 transition-colors"
        >
          Cerrar
        </button>
      </div>
    </div>
  </div>
</template>

