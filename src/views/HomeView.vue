<script setup>
import data from '@/data/homeData.js'
import PressComponent from '@/components/home/PressComponent.vue'
import TVComponent from '@/components/home/TVComponent.vue'
import PodcastsComponent from '@/components/home/PodcastsComponent.vue'
import MusicComponent from '@/components/home/MusicComponent.vue'
import GamesComponent from '@/components/home/GamesComponent.vue'
</script>
<template>
  <div class="flex w-full flex-col gap-8 md:flex-row">
    <div class="w-full">
      <PressComponent :data="data.press" />
      <TVComponent :data="data.tv" />
    </div>
    <div class="w-full">
      <PodcastsComponent :data="data.podcasts" />
      <MusicComponent :data="data.music" />
      <GamesComponent :data="data.games" />
    </div>
  </div>
</template>
