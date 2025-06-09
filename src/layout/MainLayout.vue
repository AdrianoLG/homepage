<script setup>
import { RouterView } from 'vue-router'
import { useRouter } from 'vue-router'
import { onMounted } from 'vue'

const router = useRouter()

onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key == 'ArrowLeft') {
      router.push('/')
    }
    if (e.key == 'ArrowRight') {
      router.push('/trabajo')
    }
  })
})
</script>

<template>
  <div
    class="border-primary-light border-t-4 border-b-4 border-double bg-[url(@/assets/pattern.svg)] bg-repeat"
  >
    <main class="w-full max-w-7xl px-8 py-8 md:px-16 md:py-16 lg:mx-auto 2xl:px-0">
      <RouterView />
    </main>
  </div>
</template>
