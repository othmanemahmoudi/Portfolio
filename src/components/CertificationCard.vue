<script setup lang="ts">
defineProps({
  title: { type: String, required: true },
  subtitle: { type: String, required: true },
  description: { type: String, required: true },
  date: { type: String, required: true },
  tags: { type: Array<string>, default: () => [] },
  certificateUrl: { type: String, default: '#' }
})
</script>

<template>
  <div class="w-full h-full">
    <div
      class="p-8 h-full w-full flex flex-col justify-between shadow-lg relative bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 backdrop-blur-xl rounded-2xl border border-[#CFAF71]/40 hover:scale-[1.02] transition-transform duration-300"
    >
      <!-- Coins décoratifs -->
      <div class="absolute top-0 left-0 w-20 h-20 border-t-2 border-l-2 border-[#CFAF71] rounded-tl-2xl"></div>
      <div class="absolute top-0 right-0 w-20 h-20 border-t-2 border-r-2 border-[#8B6937] rounded-tr-2xl"></div>
      <div class="absolute bottom-0 left-0 w-20 h-20 border-b-2 border-l-2 border-[#FFECC2] rounded-bl-2xl"></div>
      <div class="absolute bottom-0 right-0 w-20 h-20 border-b-2 border-r-2 border-[#CFAF71] rounded-br-2xl"></div>

      <div class="relative">
        <!-- Badge de date -->
        <div class="absolute -top-12 left-0 px-6 py-1 bg-gradient-to-r from-[#CFAF71] to-[#8B6937] rounded-full text-sm text-white font-semibold shadow-lg">
          {{ date }}
        </div>

        <!-- Contenu -->
        <h2 class="text-xl font-bold mb-2 text-[#2A2A2A] mt-4">{{ title }}</h2>
        <h3 class="text-gray-700 line-clamp-3 font-semibold mb-4 text-transparent bg-clip-text bg-gradient-to-r from-[#CFAF71] via-[#FFECC2] to-[#8B6937]">
          {{ subtitle }}
        </h3>
        <p class="text-gray-700 line-clamp-3  text-[#2A2A2A]/80 mb-6">
          {{ description }}
        </p>

        <!-- Tags dynamiques -->
        <div v-if="tags.length > 0" class="flex flex-wrap gap-3 mb-6">
          <span
            v-for="(tag, index) in tags"
            :key="index"
            class="px-3 rounded-full text-white bg-gradient-to-r from-[#CFAF71] to-[#8B6937] hover:scale-110 transition-transform cursor-pointer shadow-md"
          >
            {{ tag }}
          </span>
        </div>

        <!-- Bouton certificat -->
        <a
          :href="certificateUrl"
          target="_blank"
          class="group inline-flex items-center justify-center gap-2 px-6 py-1 rounded-full bg-gradient-to-r from-[#CFAF71] to-[#8B6937] hover:opacity-90 transition-opacity text-white font-semibold shadow-lg"
        >
          Voir le certificat
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="group-hover:rotate-12 transition-transform duration-300"
            width="20"
            height="20"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <circle cx="12" cy="8" r="7"></circle>
            <polyline points="8.21 13.89 7 23 12 20 17 23 15.79 13.88"></polyline>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>