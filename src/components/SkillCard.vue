<script setup lang="ts">
defineProps({
  name: { type: String, required: true },
  icon: { type: String, required: true },
  category: { type: String, required: true },
  bgImage: { type: String, default: '' }
})
</script>

<template>
  <div 
    class="relative group  aspect-square rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-all duration-300 hover:scale-105 cursor-pointer"
  >
    <!-- Image de fond si fournie -->
    <div 
      v-if="bgImage"
      class="absolute inset-0 bg-cover bg-center opacity-15 group-hover:opacity-25 transition-opacity duration-500"
      :style="{ backgroundImage: `url(${bgImage})` }"
    ></div>
    
    <!-- Gradient de fond animé -->
    <div class="absolute inset-0 bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 group-hover:from-[#CFAF71]/30 group-hover:via-[#FFECC2]/30 group-hover:to-[#8B6937]/30 transition-all duration-300"></div>
    
    <!-- Bordure dorée animée -->
    <div class="absolute inset-0 border border-[#CFAF71]/40 rounded-xl group-hover:border-[#CFAF71]/80 transition-all duration-300"></div>
    
    <!-- Badge catégorie (réduit) -->
    <div class="absolute top-2 right-2 bg-[#CFAF71] text-white text-[10px] font-bold px-2 py-0.5 rounded-full">
      {{ category }}
    </div>
    
    <!-- Contenu -->
    <div class="relative h-full flex flex-col items-center justify-center p-3 backdrop-blur-sm">
      <!-- Icône (réduite) -->
      <div class="text-4xl mb-2 transform group-hover:scale-110 transition-all duration-300">
        {{ icon }}
      </div>
      
      <!-- Nom de la compétence (réduit) -->
      <h3 class="text-sm font-bold text-[#2A2A2A] mb-1 group-hover:text-[#CFAF71] transition-colors duration-300 text-center line-clamp-1">
        {{ name }}
      </h3>

    </div>
  </div>
</template>

<style scoped>
/* Simplification - moins d'animations pour performances */
.line-clamp-1 {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>