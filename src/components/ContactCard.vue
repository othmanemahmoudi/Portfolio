<script setup lang="ts">
defineProps({
  platform: { type: String, required: true },
  icon: { type: String, required: true },
  value: { type: String, required: true },
  link: { type: String, required: true },
  bgImage: { type: String, default: '' },
  color: { type: String, default: 'from-[#CFAF71] to-[#8B6937]' }
})
</script>

<template>
  <a
    :href="link"
    target="_blank"
    class="relative group w-full sm:w-[48%] lg:w-[30%] aspect-[4/3] rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-500 hover:scale-105 cursor-pointer"
  >
    <!-- Image de fond si fournie -->
    <div 
      v-if="bgImage"
      class="absolute inset-0 bg-cover bg-center opacity-10 group-hover:opacity-20 transition-opacity duration-500"
      :style="{ backgroundImage: `url(${bgImage})` }"
    ></div>
    
    <!-- Gradient de fond animé -->
    <div class="absolute inset-0 bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 group-hover:from-[#CFAF71]/30 group-hover:via-[#FFECC2]/30 group-hover:to-[#8B6937]/30 transition-all duration-500"></div>
    
    <!-- Particules flottantes -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="contact-particle contact-particle-1"></div>
      <div class="contact-particle contact-particle-2"></div>
      <div class="contact-particle contact-particle-3"></div>
    </div>
    
    <!-- Bordure dorée animée -->
    <div class="absolute inset-0 border-2 border-[#CFAF71]/40 rounded-2xl group-hover:border-[#CFAF71]/80 transition-all duration-500"></div>
    
    <!-- Badge "Cliquez ici" au survol -->
    <div class="absolute top-4 right-4 bg-[#CFAF71] text-white text-xs font-bold px-3 py-1 rounded-full opacity-0 group-hover:opacity-100 transition-opacity duration-300">
      Cliquez ici
    </div>
    
    <!-- Contenu -->
    <div class="relative h-full flex flex-col items-center justify-center p-6 backdrop-blur-sm">
      <!-- Icône -->
      <div class="text-7xl mb-4 transform group-hover:scale-110 group-hover:rotate-12 transition-all duration-500">
        {{ icon }}
      </div>
      
      <!-- Plateforme -->
      <h3 class="text-2xl font-bold text-[#2A2A2A] mb-3 group-hover:text-[#CFAF71] transition-colors duration-300">
        {{ platform }}
      </h3>
      
      <!-- Valeur (email, pseudo, etc.) -->
      <p class="text-base text-[#2A2A2A]/70 font-medium text-center px-2 break-all">
        {{ value }}
      </p>
      
      <!-- Indicateur de lien -->
      <div class="mt-4 flex items-center gap-2 text-[#CFAF71] opacity-0 group-hover:opacity-100 transition-opacity duration-300">
        <span class="text-sm font-semibold">Contacter</span>
        <svg class="w-4 h-4 animate-bounce-x" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
        </svg>
      </div>
    </div>
  </a>
</template>

<style scoped>
/* Animation des particules */
.contact-particle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: #CFAF71;
  border-radius: 50%;
  opacity: 0;
  animation: float-contact 6s infinite;
}

.contact-particle-1 {
  left: 20%;
  animation-delay: 0s;
}

.contact-particle-2 {
  left: 50%;
  animation-delay: 2s;
}

.contact-particle-3 {
  left: 80%;
  animation-delay: 4s;
}

@keyframes float-contact {
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

/* Animation flèche horizontale */
@keyframes bounce-x {
  0%, 100% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(5px);
  }
}

.animate-bounce-x {
  animation: bounce-x 1s ease-in-out infinite;
}

/* Animation au survol */
.group:hover .contact-particle {
  animation-duration: 3s;
}
</style>