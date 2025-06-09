<script setup>
import { onMounted } from 'vue'
import { ref } from 'vue'

const { data } = defineProps({
  data: {
    type: Object,
    required: true
  }
})

const coursesRef = ref(null)

onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key === '5') {
      coursesRef.value?.focus()
    }
  })
})
</script>

<template>
  <div class="group/Section mb-12" ref="coursesRef" tabindex="-1">
    <h2 class="mb-4 flex justify-between text-3xl">
      <span>Cursos</span>
      <span class="text-primary-opposite hidden text-lg group-focus/Section:hidden md:inline"
        >[5]</span
      >
    </h2>
    <div
      class="border-primary-light group-focus/Section:inset-ring-primary-opposite grid grid-cols-2 gap-4 rounded-md border-1 bg-white p-4 group-focus/Section:inset-ring-2 sm:grid-cols-3 md:grid-cols-2 lg:grid-cols-3"
    >
      <a
        v-for="course in data"
        :key="course.title"
        :href="course.url"
        target="_blank"
        class="group relative block w-full overflow-hidden rounded-md transition-all duration-200 hover:shadow-md focus:shadow-md"
      >
        <img
          :src="`src/assets/logos/avif/${course.img}_ov.avif`"
          :alt="course.title"
          :title="course.title"
          class="absolute top-0 left-0 w-full opacity-0 transition-all duration-200 group-hover:opacity-100 group-focus:opacity-100"
        />
        <img
          :src="`src/assets/logos/avif/${course.img}.avif`"
          :alt="course.title"
          :title="course.title"
          class="relative z-10 w-full"
        />
      </a>
    </div>
  </div>
</template>
