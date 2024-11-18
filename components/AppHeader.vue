<template>
  <nav class="bg-white shadow-md">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <!-- Logo -->
        <div class="flex-shrink-0 flex items-center">
          <NuxtLink to="/" class="text-xl font-bold text-blue-500">Portfolio</NuxtLink>
        </div>

        <!-- Mobile menu button -->
        <div class="flex items-center md:hidden">
          <button
            type="button"
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-900 hover:bg-gray-100 focus:outline-none"
            aria-controls="mobile-menu"
            aria-expanded="false"
            @click="isOpen = !isOpen"
          >
            <svg
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                :class="{ 'hidden': isOpen, 'inline-flex': !isOpen }"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                :class="{ 'hidden': !isOpen, 'inline-flex': isOpen }"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>

   
        <div class="hidden md:flex space-x-8">
          <NuxtLink
            to="/"
            class="text-gray-500 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium flex justify-center items-center"
            active-class="text-blue-600"
          >
            Home
          </NuxtLink>
          <NuxtLink
            to="/projects"
            class="text-gray-500 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium flex justify-center items-center"
            active-class="text-blue-600"
          >
            Projects
          </NuxtLink>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div
      class="md:hidden"
      :class="{ 'block': isOpen, 'hidden': !isOpen }"
      id="mobile-menu"
    >
      <div class="space-y-1 px-2 pt-2 pb-3 sm:px-3">
        <NuxtLink
          to="/home"
          class="text-gray-500 hover:text-gray-900 block px-3 py-2 rounded-md text-base font-medium"
          active-class="text-blue-600"
        >
          Home
        </NuxtLink>
        <NuxtLink
          to="/projects"
          class="text-gray-500 hover:text-gray-900 block px-3 py-2 rounded-md text-base font-medium"
          active-class="text-blue-600"
        >
        Projects
        </NuxtLink>
      </div>
    </div>
  </nav>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const isOpen = ref(false);
</script>

<style scoped>
</style>
