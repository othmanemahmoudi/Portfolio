<script setup lang="ts">
defineProps<{
  platform: string
  icon: string
  value: string
  link: string
  bgImage: string
}>()
</script>

<template>
  <a
    :href="link"
    target="_blank"
    rel="noopener noreferrer"
    class="group relative w-72 h-40 rounded-xl overflow-hidden shadow-lg transform transition duration-500 hover:scale-105 hover:rotate-1"
  >
    <!-- Background image -->
    <div
      class="absolute inset-0 bg-cover bg-center transition duration-500 group-hover:blur-sm group-hover:brightness-75"
      :style="{ backgroundImage: `url(${bgImage})` }"
    ></div>

    <!-- Overlay gradient -->
    <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent"></div>

    <!-- Content -->
    <div class="relative z-10 flex flex-col items-center justify-center h-full text-white text-center px-4">
      <span class="text-4xl mb-2 transition-transform duration-500 group-hover:scale-125">
        {{ icon }}
      </span>
      <h3 class="text-xl font-bold">{{ platform }}</h3>
      <p class="text-sm opacity-80">{{ value }}</p>
    </div>

    <!-- Creative hover effect: glowing border -->
    <div class="absolute inset-0 rounded-xl border-2 border-transparent group-hover:border-[#CFAF71] transition duration-500"></div>
  </a>
</template>
