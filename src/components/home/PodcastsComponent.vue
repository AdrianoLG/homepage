<script setup>
import { onMounted } from 'vue'
import { ref } from 'vue'

const { data } = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const podcastsRef = ref(null)

onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key === '3') {
      podcastsRef.value?.focus()
    }
  })
})
</script>

<template>
  <section class="group/Section mb-12" ref="podcastsRef" tabindex="-1">
    <h1 class="mb-4 flex justify-between text-3xl">
      <span>Podcasts</span>
      <span class="text-primary-opposite hidden text-lg group-focus/Section:hidden md:inline"
        >[3]</span
      >
    </h1>
    <div
      class="border-primary-light group-focus/Section:inset-ring-primary-opposite relative grid grid-cols-4 gap-4 rounded-md border-1 bg-white p-4 group-focus/Section:inset-ring-2 sm:grid-cols-5 md:grid-cols-4 lg:grid-cols-6"
    >
      <a
        v-for="podcast in data"
        :key="podcast.title"
        :href="podcast.url"
        target="_blank"
        class="group relative block w-full overflow-hidden rounded-full transition-all duration-200 hover:scale-110 hover:rotate-3 hover:shadow-md focus:scale-110 focus:rotate-3 focus:shadow-md"
      >
        <img
          :src="`src/assets/logos/avif/${podcast.img}.avif`"
          :alt="podcast.title"
          :title="podcast.title"
          class="relative z-10 w-full"
        />
      </a>
    </div>
  </section>
</template>
