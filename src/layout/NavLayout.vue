<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <nav class="flex w-full max-w-7xl gap-1.5 px-8 py-8 md:px-16 md:py-16 lg:mx-auto 2xl:px-0">
    <RouterLink
      class="border-primary hover:bg-primary rounded-md border-1 px-12 py-2 hover:text-white hover:shadow-md"
      exactActiveClass="bg-primary text-white shadow-md"
      to="/"
      >Casa</RouterLink
    >
    <RouterLink
      class="border-primary hover:bg-primary rounded-md border-1 px-12 py-2 hover:text-white hover:shadow-md"
      exactActiveClass="bg-primary text-white shadow-md"
      to="/trabajo"
      >Trabajo</RouterLink
    >
  </nav>
</template>
