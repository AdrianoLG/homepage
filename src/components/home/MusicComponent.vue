<script setup>
import { onMounted } from 'vue'
import { ref } from 'vue'

const { data } = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const musicRef = ref(null)

onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key === '4') {
      musicRef.value?.focus()
    }
  })
})
</script>

<template>
  <section class="group/Section mb-12" ref="musicRef" tabindex="-1">
    <h1 class="mb-4 flex justify-between text-3xl">
      <span>Música</span>
      <span class="text-primary-opposite hidden text-lg group-focus/Section:hidden md:inline"
        >[4]</span
      >
    </h1>
    <div
      class="border-primary-light group-focus/Section:inset-ring-primary-opposite relative grid grid-cols-2 gap-4 rounded-md border-1 bg-white p-4 group-focus/Section:inset-ring-2 sm:grid-cols-3"
    >
      <a
        v-for="app in data"
        :key="app.title"
        :href="app.url"
        target="_blank"
        class="group block w-full overflow-hidden rounded-md contrast-100 transition-all duration-200 hover:shadow-md hover:contrast-80 hover:hue-rotate-90 focus:shadow-md focus:contrast-80 focus:hue-rotate-90"
      >
        <img
          :src="`src/assets/logos/avif/${app.img}.avif`"
          :alt="app.title"
          :title="app.title"
          class="relative z-10 w-full"
        />
      </a>
    </div>
  </section>
</template>
