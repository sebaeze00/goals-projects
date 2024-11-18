<script setup lang="ts">
import { ref } from 'vue';

interface CardMainProps {
  name: string;
  status: string;
  id: number;
  url: string;
  species: string;
  gender: string;
  origin: {
    name: string;
  };
}

const props = defineProps<CardMainProps>();
const isModalOpen = ref(false);

const getStatusColor = (status: string) => {
  switch (status.toLowerCase()) {
    case 'alive':
      return 'bg-green-500';
    case 'dead':
      return 'bg-red-500';
    default:
      return 'bg-gray-500';
  }
}

const toggleModal = () => {
  isModalOpen.value = !isModalOpen.value;
  if (isModalOpen.value) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = 'auto';
  }
}

// CERRAR MODAL CON EL ESC
const handleKeydown = (event: KeyboardEvent) => {
  if (event.key === 'Escape' && isModalOpen.value) {
    toggleModal();
  }
}
// ESCUCHA CUANDO SE APRETA LA TECLA
onMounted(() => {
  window.addEventListener('keydown', handleKeydown);
});

//DEJA DE ESCUCHAR CUANDO SE APRETA LA TECLA
onUnmounted(() => {
  window.removeEventListener('keydown', handleKeydown);
});
</script>

<template>
  <div>
    
    <!-- CARD NORMAL -->
    <div 
      class="w-64 rounded-lg overflow-hidden shadow-lg transition-transform duration-300 hover:scale-105 bg-slate-800 text-white mb-10"
    >
      <div class="relative">
        <img 
          :src="url" 
          :alt="name"
          class="w-full h-64 object-cover"
        >
        <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-slate-900 to-transparent h-20"></div>
      </div>

      <div class="p-5">
        <div class="flex items-center justify-between mb-3">
          <h2 class="text-xl font-bold">#{{ id }} {{ name }}</h2>
        </div>
        <div class="flex items-center gap-2 mb-4">
          <span 
            class="w-3 h-3 rounded-full" 
            :class="getStatusColor(status)"
          ></span>
          <span class="text-gray-300">{{ status }}</span>
        </div>

        <button 
          @click="toggleModal"
          class="inline-block bg-purple-600 text-white px-4 py-2 rounded-lg hover:bg-purple-700 transition-colors duration-300 text-center w-full"
        >
          Read more
        </button>
      </div>
    </div>


       <!-- TRANCISIÓN Y PANTALLAS ANTES DEL MODAL -->

    <Transition
      enter-active-class="transition duration-300 ease-out"
      enter-from-class="transform scale-95 opacity-0"
      enter-to-class="transform scale-100 opacity-100"
      leave-active-class="transition duration-200 ease-in"
      leave-from-class="transform scale-100 opacity-100"
      leave-to-class="transform scale-95 opacity-0"
    >
      <div
        v-if="isModalOpen"
        class="fixed inset-0 z-50 flex items-center justify-center p-4"
      >
     
        <div 
          class="fixed inset-0 bg-black bg-opacity-50 transition-opacity"
          @click="toggleModal"
        ></div>


        <!-- MODAL -->
        <div 
          class="relative z-50 w-full max-w-2xl bg-slate-800 rounded-xl shadow-xl overflow-hidden"
        >
          <div class="flex flex-col md:flex-row">
            <img 
              :src="url" 
              :alt="name"
              class="w-full md:w-1/2 h-64 md:h-auto object-cover"
            >
            <div class="p-6 flex flex-col flex-1">
              <div class="flex items-center justify-between mb-4">
                <h2 class="text-2xl font-bold text-white">#{{ id }} {{ name }}</h2>
                <button 
                  @click="toggleModal"
                  class="text-gray-400 hover:text-white transition-colors"
                >
                  <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                  </svg>
                </button>
              </div>

              <div class="flex items-center gap-2 mb-4">
                <span 
                  class="w-3 h-3 rounded-full" 
                  :class="getStatusColor(status)"
                ></span>
                <span class="text-gray-300">{{ status }}</span>
              </div>

              <div class="space-y-3 text-gray-300">
                <p><span class="font-semibold text-white">Species:</span> {{ species }}</p>
                <p><span class="font-semibold text-white">Gender:</span> {{ gender }}</p>
                <p><span class="font-semibold text-white">Origin:</span> {{ origin.name }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </div>
</template>