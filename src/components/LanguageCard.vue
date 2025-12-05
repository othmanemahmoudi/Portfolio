<script setup lang="ts">
defineProps({
  language: { type: String, required: true },
  flag: { type: String, required: true },
  level: { type: String, required: true }

})
</script>

<template>
  <div 
    class="relative group w-full sm:w-[48%] lg:w-[30%] aspect-[4/3] rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 hover:scale-105 cursor-pointer"
  >

    
    <!-- Gradient de fond animé -->
    <div class="absolute inset-0 bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 group-hover:from-[#CFAF71]/30 group-hover:via-[#FFECC2]/30 group-hover:to-[#8B6937]/30 transition-all duration-500"></div>
    
    <!-- Particules flottantes -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="particle particle-1"></div>
      <div class="particle particle-2"></div>
      <div class="particle particle-3"></div>
    </div>
    
    <!-- Bordure dorée animée -->
    <div class="absolute inset-0 border-2 border-[#CFAF71]/40 rounded-2xl group-hover:border-[#CFAF71]/80 transition-all duration-500"></div>
    
    <!-- Contenu -->
    <div class="relative h-full flex flex-col items-center justify-center p-6 backdrop-blur-sm">
      <!-- Drapeau -->
      <div class="text-8xl mb-4 transform group-hover:scale-110 group-hover:rotate-6 transition-all duration-500">
        {{ flag }}
      </div>
      
      <!-- Langue -->
      <h3 class="text-2xl font-bold text-[#2A2A2A] mb-2 group-hover:text-[#CFAF71] transition-colors duration-300">
        {{ language }}
      </h3>
      
      <!-- Niveau -->
      <p class="text-lg text-[#2A2A2A]/70 mb-4 font-semibold">
        {{ level }}
      </p>
    </div>
  </div>
</template>

<style scoped>
/* Animation des particules */
.particle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: #CFAF71;
  border-radius: 50%;
  opacity: 0;
  animation: float 6s infinite;
}

.particle-1 {
  left: 20%;
  animation-delay: 0s;
}

.particle-2 {
  left: 50%;
  animation-delay: 2s;
}

.particle-3 {
  left: 80%;
  animation-delay: 4s;
}

@keyframes float {
  0% {
    transform: translateY(100%);
    opacity: 0;
  }
  50% {
    opacity: 0.8;
  }
  100% {
    transform: translateY(-100%);
    opacity: 0;
  }
}

/* Animation au survol */
.group:hover .particle {
  animation-duration: 3s;
}
</style>