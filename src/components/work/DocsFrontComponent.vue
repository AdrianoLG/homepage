<script setup>
import { onMounted } from 'vue'
import { ref } from 'vue'

const { data } = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const docsFrontRef = ref(null)

onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key === '1') {
      docsFrontRef.value?.focus()
    }
  })
})
</script>

<template>
  <div class="group/Section mb-8" ref="docsFrontRef" tabindex="-1">
    <h2 class="mb-4 flex justify-between text-xl">
      <span>Front</span>
      <span class="text-primary-opposite hidden text-lg group-focus/Section:hidden md:inline"
        >[1]</span
      >
    </h2>
    <div
      class="border-primary-light group-focus/Section:inset-ring-primary-opposite relative grid grid-cols-3 gap-4 rounded-md border-1 bg-white p-4 group-focus/Section:inset-ring-2 sm:grid-cols-4 md:grid-cols-3 lg:grid-cols-4"
    >
      <a
        v-for="doc in data"
        :key="doc.title"
        :href="doc.url"
        target="_blank"
        class="group block w-full overflow-hidden rounded-md contrast-100 transition-all duration-200 hover:shadow-md hover:contrast-80 hover:hue-rotate-90 focus:shadow-md focus:contrast-80 focus:hue-rotate-90"
      >
        <img
          :src="`src/assets/logos/avif/${doc.img}.avif`"
          :alt="doc.title"
          :title="doc.title"
          class="relative z-10 w-full"
        />
      </a>
    </div>
  </div>
</template>
