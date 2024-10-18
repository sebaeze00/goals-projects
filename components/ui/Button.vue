<script setup>
import { ref } from 'vue';

// Estado del botón
const buttonText = ref('Click me');
const desactivar = ref(false);

// Función que maneja el evento de clic
const handleClick = () => {
  alert('Botón presionado!');
  desactivar.value = true
};

</script>


<template>
    <button :disabled="desactivar" @click="handleClick" :class="[
      desactivar ? 'bg-gray-500 cursor-not-allowed' : 'bg-blue-500 hover:bg-blue-700 cursor-pointer', 'text-white font-bold py-2 px-4 rounded transition'
    ]">
      {{ buttonText }}
    </button>
  </template>
  

  