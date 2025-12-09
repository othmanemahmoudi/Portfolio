<template>
  <div class="w-full overflow-hidden py-10 relative">
    <div class="banner-track">
      <div class="banner-content flex gap-6">
        <img
          v-for="(img, index) in duplicatedImages"
          :key="index"
          :src="img"
          class="h-80 w-70 rounded-xl shadow-md object-cover flex-shrink-0"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  images: string[]
}>()

// On double la liste pour avoir deux sets complets
const duplicatedImages = computed(() => {
  if (props.images.length === 0) return []
  return [...props.images, ...props.images]
})
</script>

<style scoped>
.banner-track {
  overflow: hidden;
}

.banner-content {
  display: flex;
  gap: 1.5rem;
  width: max-content;
  animation: scroll 25s linear infinite;
}

@keyframes scroll {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-50%);
  }
}

.banner-content:hover {
  animation-play-state: paused;
}
</style>
