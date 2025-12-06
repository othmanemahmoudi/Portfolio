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
    class="group relative w-72 h-44 rounded-xl overflow-hidden shadow-xl transform transition duration-500 hover:scale-105"
  >
    <!-- Fond animé -->
    <div
      class="absolute inset-0 bg-cover bg-center transition-all duration-700 group-hover:scale-110 group-hover:rotate-1"
      :style="{ backgroundImage: `url(${bgImage})` }"
    ></div>

    <!-- Overlay avec effet de verre -->
    <div class="absolute inset-0 bg-gradient-to-br from-black/60 via-black/30 to-transparent backdrop-blur-sm"></div>

    <!-- Contenu -->
    <div class="relative z-10 flex flex-col items-center justify-center h-full text-white text-center px-4">
      <!-- Icône avec effet néon -->
      <span
        class="text-5xl mb-2 transition-transform duration-500 group-hover:scale-125 group-hover:drop-shadow-[0_0_10px_#CFAF71]"
      >
        {{ icon }}
      </span>
      <h3 class="text-xl font-bold tracking-wide group-hover:text-[#CFAF71] transition-colors">
        {{ platform }}
      </h3>
      <p class="text-sm opacity-80 group-hover:opacity-100 transition">{{ value }}</p>
    </div>

    <!-- Bordure animée -->
    <div class="absolute inset-0 rounded-xl border-2 border-transparent group-hover:border-[#CFAF71] animate-pulse"></div>

    <!-- Effet de particules décoratives -->
    <div class="absolute -top-10 -left-10 w-40 h-40 bg-[#CFAF71]/20 rounded-full blur-3xl group-hover:opacity-100 opacity-0 transition"></div>
    <div class="absolute -bottom-10 -right-10 w-40 h-40 bg-[#CFAF71]/20 rounded-full blur-3xl group-hover:opacity-100 opacity-0 transition"></div>
  </a>
</template>
