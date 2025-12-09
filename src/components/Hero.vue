<script setup lang="ts">
const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    const headerHeight = 80
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - headerHeight

    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
  }
}
</script>

<template>
  <section id="hero" class="relative min-h-screen flex items-center justify-center">
    <div class="container mx-auto">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Contenu texte -->
        <div class="text-center lg:text-left space-y-6 animate-fade-in">
          <div class="inline-block">
            <span class="text-sm font-semibold text-[#CFAF71] bg-[#2A2A2A] px-4 py-2 rounded-full">
              👋 Bonjour, je suis
            </span>
          </div>
          
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-white leading-tight">
            <span class="block text-[#2A2A2A]">Développeur</span>
            <span class="block text-[#CFAF71]">Python Full Stack</span>
          </h1>
          
          <p class="text-lg md:text-xl text-[#2A2A2A] leading-relaxed max-w-3xl mx-auto lg:mx-0">
            Passionné par le développement Full Stack, je crée des applications 
            modernes et performantes en utilisant Python, Java, Docker, Vue et bien plus encore.
          </p>
          
          <div class="flex flex-wrap gap-4 justify-center lg:justify-start">
            <button 
              @click="scrollToSection('contact')"
              class="px-8 py-3 bg-transparent text-[#CFAF71] font-semibold rounded-lg border-2 border-[#CFAF71] hover:bg-[#CFAF71]/10 transition-all duration-300 transform hover:scale-105"
            >
              Me contacter
            </button>
            <button 
              @click="scrollToSection('projects')"
              class="px-8 py-3 bg-transparent text-[#CFAF71] font-semibold rounded-lg border-2 border-[#CFAF71] hover:bg-[#CFAF71]/10 transition-all duration-300 transform hover:scale-105"
            >
              Voir mes projets
            </button>
          </div>
          
          <!-- Technologies -->
          <div class="pt-6">
            <p class="text-sm text-[#2A2A2A] mb-3">Technologies que j'utilise :</p>
            <div class="flex flex-wrap gap-3 justify-center lg:justify-start">
              <span class="px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">Python</span>
              <span class="px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">Java</span>
              <span class="px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">FastAPI</span>
              <span class="px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">Vue</span>
              <span class="px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">Linux</span>
              <span class="px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">Docker</span>
              <a href="#skills" 
                class="hover:text-[#CFAF71] ml-4 px-4 py-2 bg-[#2A2A2A] text-white rounded-lg text-sm font-medium">
                Voir toutes les compétences
              </a>
            </div>
          </div>
        </div>
        
        <!-- Photo de profil -->
        <div class="flex justify-center lg:justify-end animate-fade-in-delay mx-15">
          <div class="relative">
            <!-- Cercle décoratif en arrière-plan -->
            <div class="absolute inset-0 bg-gradient-to-br from-[#FFECC2]/90 via-[#CFAF71]/85 to-[#8B6937]/75 rounded-full blur-3xl opacity-20 animate-pulse"></div>
            
            <!-- Photo de profil -->
            <div class="relative w-80 h-80 md:w-96 md:h-96 lg:w-[500px] lg:h-[500px] xl:w-[600px] xl:h-[600px]">
              <div class="absolute inset-0 bg-gradient-to-br from-[#CFAF71] to-[#CFAF71]/70 rounded-full p-1 animate-spin-slow">
                <div class="w-full h-full bg-[#111111] rounded-full"></div>
              </div>
              <div class="absolute inset-2 rounded-full overflow-hidden border-4 border-[#CFAF71] shadow-2xl">

                <img 
                  src="../assets/othmane.png" 
                  alt="Othmane - Développeur Python Full Stack"
                  class="w-full h-full object-cover"
                />
                <!-- Si vous avez une image locale, utilisez : -->
                <!-- <img src="/src/assets/profile.jpg" alt="Othmane" class="w-full h-full object-cover" /> -->
              </div>
            </div>
            
            <!-- Badge flottant -->
            <div class="absolute -bottom-4 -right-4 bg-[#2A2A2A] rounded-lg shadow-xl p-4 border-2 border-[#CFAF71] animate-bounce-slow">
              <div class="flex items-center gap-2">
                <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                <span class="text-sm font-semibold text-[#CFAF71] ">Disponible</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Scroll indicator -->
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
        <button 
          @click="scrollToSection('about')"
          class="flex flex-col items-center text-gray-400 hover:text-[#CFAF71] transition-colors"
          aria-label="Scroll down"
        >
          <span class="text-sm mb-2 text-[#CFAF71]">Découvrir</span>
          <svg class="w-6 h-6 text-[#CFAF71]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fade-in-delay {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes spin-slow {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes bounce-slow {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-fade-in {
  animation: fade-in 0.8s ease-out;
}

.animate-fade-in-delay {
  animation: fade-in-delay 2s ease-out 0.2s both;
}

.animate-spin-slow {
  animation: spin-slow 20s linear infinite;
}

.animate-bounce-slow {
  animation: bounce-slow 3s ease-in-out infinite;
}
@keyframes spin-safe {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.animate-spin-safe {
  animation: spin-safe 20s linear infinite;
  transform-origin: center center;
  will-change: transform;
}
</style>

