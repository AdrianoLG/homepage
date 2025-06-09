<script setup>
import DocsFrontComponent from '@/components/work/DocsFrontComponent.vue'
import DocsBackComponent from '@/components/work/DocsBackComponent.vue'
import DocsOtherComponent from '@/components/work/DocsOtherComponent.vue'

const { dataFront, dataBack } = defineProps({
  dataFront: {
    type: Object,
    required: true
  },
  dataBack: {
    type: Object,
    required: true
  },
  dataOther: {
    type: Object,
    required: true
  }
})
</script>
<template>
  <section>
    <h1 class="mb-8 text-3xl">Documentación</h1>
    <div class="mb-4 grid grid-cols-1 gap-4 md:mb-8 md:grid-cols-2">
      <DocsFrontComponent :data="dataFront" />
      <div class="mb-8">
        <DocsBackComponent :data="dataBack" />
        <DocsOtherComponent :data="dataOther" />
      </div>
    </div>
  </section>
</template>
