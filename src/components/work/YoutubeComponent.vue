<script setup>
import { onMounted } from 'vue'
import { ref } from 'vue'

const { data } = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const youTubeRef = ref(null)

onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key === '4') {
      youTubeRef.value?.focus()
    }
  })
})
</script>

<template>
  <section
    class="group/Section mt-8 mb-16 grid-cols-3 gap-4 md:grid-cols-6"
    ref="youTubeRef"
    tabindex="-1"
  >
    <h2 class="mb-4 flex justify-end text-xl">
      <span class="text-primary-opposite hidden text-lg group-focus/Section:hidden md:inline"
        >[4]</span
      >
    </h2>
    <div
      class="border-primary-light group-focus/Section:inset-ring-primary-opposite relative grid grid-cols-4 gap-4 rounded-md border-1 bg-white p-4 group-focus/Section:inset-ring-2 sm:grid-cols-6 md:grid-cols-9 lg:grid-cols-12"
    >
      <a
        v-for="channel in data"
        :key="channel.title"
        :href="channel.url"
        target="_blank"
        class="group relative block w-full overflow-hidden rounded-full transition-all duration-200 hover:scale-110 hover:rotate-3 hover:shadow-md focus:scale-110 focus:rotate-3 focus:shadow-md"
      >
        <img
          :src="`./logos/avif/${channel.img}.avif`"
          :alt="channel.title"
          :title="channel.title"
          class="relative z-10 w-full"
        />
      </a>
    </div>
  </section>
</template>
