<script setup>
import data from '@/data/workData.js'
import DocsComponent from '@/components/work/DocsComponent.vue'
import YoutubeComponent from '@/components/work/YoutubeComponent.vue'
import CoursesComponent from '@/components/work/CoursesComponent.vue'
import ToolsComponent from '@/components/work/ToolsComponent.vue'
</script>

<template>
  <div class="flex w-full flex-col gap-8 md:flex-row">
    <div class="w-full">
      <DocsComponent :dataFront="data.front" :dataBack="data.back" :dataOther="data.others" />
      <YoutubeComponent :data="data.youtube" />
      <section class="mb-4 grid grid-cols-1 gap-4 md:mb-8 md:grid-cols-2">
        <CoursesComponent :data="data.courses" />
        <ToolsComponent :data="data.tools" />
      </section>
    </div>
  </div>
</template>

<style></style>
