<template>
  <div
    class="w-64 h-40 rounded-xl overflow-hidden shadow-lg relative group cursor-pointer transition-transform transform hover:scale-105"
  >
    <!-- Background -->
    <img
      :src="bgImage"
      alt="hobie image"
      class="w-full h-full object-cover absolute inset-0 opacity-80 group-hover:opacity-100 transition"
    />

    <!-- Overlay -->
    <div class="absolute inset-0 bg-black/40 group-hover:bg-black/30 transition"></div>

    <!-- Text content -->
    <div class="absolute inset-0 flex flex-col items-center justify-center text-white">
      <span class="text-4xl mb-2">{{ icon }}</span>
      <h3 class="text-xl font-semibold">{{ name }}</h3>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  name: String,
  icon: String,
  bgImage: String
})
</script>
