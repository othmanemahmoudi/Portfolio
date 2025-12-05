<template>
  <div class="w-full overflow-hidden py-10 relative">
    <div class="banner-track flex gap-6">
      <!-- Triple série pour un effet plus fluide -->
      <img
        v-for="(img, index) in images"
        :key="'img-a-' + index"
        :src="img"
        class="h-40 w-auto rounded-xl shadow-md object-cover flex-shrink-0"
      />
      <img
        v-for="(img, index) in images"
        :key="'img-b-' + index"
        :src="img"
        class="h-40 w-auto rounded-xl shadow-md object-cover flex-shrink-0"
      />
      <img
        v-for="(img, index) in images"
        :key="'img-c-' + index"
        :src="img"
        class="h-40 w-auto rounded-xl shadow-md object-cover flex-shrink-0"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  images: string[]
}>()
</script>

<style scoped>
.banner-track {
  display: flex;
  animation: infiniteSlide 30s linear infinite;
  will-change: transform;
}

@keyframes infiniteSlide {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-66.666%);
  }
}

.banner-track:hover {
  animation-play-state: paused;
}
</style>