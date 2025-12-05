<template>
  <div class="w-full overflow-hidden py-10 relative">
    <div class="banner-track flex gap-6">
      <!-- Dupliquer les images jusqu'à en avoir un nombre suffisant -->
      <img
        v-for="(img, index) in duplicatedImages"
        :key="index"
        :src="img"
        class="h-auto w-80 rounded-xl shadow-md object-cover flex-shrink-0"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  images: string[]
}>()

// Dupliquer les images pour en avoir au moins 10 dans la piste
const duplicatedImages = computed(() => {
  const duplicated: string[] = []
  const minImages = 10 // Nombre minimum d'images dans la piste
  
  // Si on n'a pas d'images, retourner un tableau vide
  if (props.images.length === 0) return duplicated
  
  // Dupliquer les images jusqu'à atteindre minImages
  let i = 0
  while (duplicated.length < minImages) {
    duplicated.push(props.images[i % props.images.length])
    i++
  }
  
  return duplicated
})
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
    /* On décale de la moitié de la largeur totale de la piste (car on a dupliqué les images) */
    transform: translateX(-50%);
  }
}

.banner-track:hover {
  animation-play-state: paused;
}
</style>