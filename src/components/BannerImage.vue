<template>
  <div class="w-full overflow-hidden py-10">
    <div class="banner-track flex gap-6">
      <!-- première série -->
      <img
        v-for="(img, index) in images"
        :key="'img-' + index"
        :src="img"
        class="h-40 w-auto rounded-xl shadow-md object-cover"
      />

      <!-- duplication pour la boucle infinie -->
      <img
        v-for="(img, index) in images"
        :key="'clone-' + index"
        :src="img"
        class="h-40 w-auto rounded-xl shadow-md object-cover"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  images: Array
})
</script>

<style scoped>
.banner-track {
  animation: infiniteSlide 25s linear infinite;
}

@keyframes infiniteSlide {
  0% {
    transform: translateX(0);
  }
  100% {
    /* 50% signifie : faire glisser juste la moitié (1 série) pour un effet sans coupure */
    transform: translateX(-50%);
  }
}
</style>
