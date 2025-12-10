<script setup lang="ts">
defineProps({
  name: { type: String, required: true },
  icon: { type: String, required: true }, // chemin vers le fichier SVG importé
  category: { type: String, required: true },
  bgImage: { type: String, default: '' },
  iconSize: { type: String, default: 'w-10 h-10' } // taille configurable
})
</script>

<template>
  <div 
    class="relative group aspect-square rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-all duration-300 hover:scale-105"
  >
    <!-- Image de fond -->
    <div 
      v-if="bgImage"
      class="absolute inset-0 bg-cover bg-center opacity-15 group-hover:opacity-25 transition-opacity duration-500"
      :style="{ backgroundImage: `url(${bgImage})` }"
    ></div>
    
    <!-- Gradient -->
    <div class="absolute inset-0 bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 group-hover:from-[#CFAF71]/30 group-hover:via-[#FFECC2]/30 group-hover:to-[#8B6937]/30 transition-all duration-300"></div>
    
    <!-- Bordure -->
    <div class="absolute inset-0 border border-[#CFAF71]/40 rounded-xl group-hover:border-[#CFAF71]/80 transition-all duration-300"></div>
    
    <!-- Badge catégorie -->
    <div class="absolute top-2 right-2 bg-[#CFAF71] text-white text-[10px] font-bold px-2 py-0.5 rounded-full">
      {{ category }}
    </div>
    
    <!-- Contenu -->
    <div class="relative h-auto flex flex-col items-center justify-center p-3 backdrop-blur-sm">
      <!-- Icône SVG locale -->
      <div class="mb-2 h-auto transform group-hover:scale-110 transition-all duration-300">
        <img :src="icon" alt="" :class="iconSize" />
      </div>
      
      <!-- Nom -->
      <h3 class="text-sm font-bold h-auto text-[#2A2A2A] mb-1 group-hover:text-[#CFAF71] transition-colors duration-300 text-center line-clamp-1">
        {{ name }}
      </h3>
    </div>
  </div>
</template>

<style scoped>
.line-clamp-1 {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
