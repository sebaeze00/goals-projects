<script setup lang="ts">
useSeoMeta({
    title: 'About Page',
    description: 'about page',
})
</script>


<template>
    <div>
        <AppHeader />
        <slot />
        <!-- <AppFooter /> -->
    </div>
</template>