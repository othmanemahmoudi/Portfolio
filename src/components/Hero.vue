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
  <section id="hero" class="relative min-h-screen flex items-center justify-center px-4 py-20 bg-gradient-to-br from-gray-50 to-white">
    <div class="container mx-auto">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Contenu texte -->
        <div class="text-center lg:text-left space-y-6 animate-fade-in">
          <div class="inline-block">
            <span class="text-sm font-semibold text-blue-600 bg-blue-50 px-4 py-2 rounded-full">
              👋 Bonjour, je suis
            </span>
          </div>
          
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight">
            <span class="block">Développeur</span>
            <span class="block text-blue-600">Python Full Stack</span>
          </h1>
          
          <p class="text-lg md:text-xl text-gray-600 leading-relaxed max-w-2xl mx-auto lg:mx-0">
            Passionné par le développement web et les technologies Python, je crée des applications 
            modernes et performantes en utilisant Django, FastAPI, React et bien plus encore.
          </p>
          
          <div class="flex flex-wrap gap-4 justify-center lg:justify-start">
            <button 
              @click="scrollToSection('contact')"
              class="px-8 py-3 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition-all duration-300 transform hover:scale-105 shadow-lg hover:shadow-xl"
            >
              Me contacter
            </button>
            <button 
              @click="scrollToSection('projects')"
              class="px-8 py-3 bg-white text-blue-600 font-semibold rounded-lg border-2 border-blue-600 hover:bg-blue-50 transition-all duration-300 transform hover:scale-105"
            >
              Voir mes projets
            </button>
          </div>
          
          <!-- Technologies -->
          <div class="pt-6">
            <p class="text-sm text-gray-500 mb-3">Technologies que j'utilise :</p>
            <div class="flex flex-wrap gap-3 justify-center lg:justify-start">
              <span class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium">Python</span>
              <span class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium">Django</span>
              <span class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium">FastAPI</span>
              <span class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium">React</span>
              <span class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium">PostgreSQL</span>
              <span class="px-4 py-2 bg-gray-100 text-gray-700 rounded-lg text-sm font-medium">Docker</span>
            </div>
          </div>
        </div>
        
        <!-- Photo de profil -->
        <div class="flex justify-center lg:justify-end animate-fade-in-delay">
          <div class="relative">
            <!-- Cercle décoratif en arrière-plan -->
            <div class="absolute inset-0 bg-gradient-to-br from-blue-400 to-blue-600 rounded-full blur-3xl opacity-20 animate-pulse"></div>
            
            <!-- Photo de profil -->
            <div class="relative w-80 h-80 md:w-96 md:h-96 lg:w-[500px] lg:h-[500px] xl:w-[600px] xl:h-[600px]">
              <div class="absolute inset-0 bg-gradient-to-br from-blue-500 to-blue-700 rounded-full p-1 animate-spin-slow">
                <div class="w-full h-full bg-white rounded-full"></div>
              </div>
              <div class="absolute inset-2 rounded-full overflow-hidden border-4 border-white shadow-2xl">
                <!-- Remplacez cette div par votre image -->
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
            <div class="absolute -bottom-4 -right-4 bg-white rounded-lg shadow-xl p-4 border-2 border-blue-100 animate-bounce-slow">
              <div class="flex items-center gap-2">
                <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                <span class="text-sm font-semibold text-gray-700">Disponible</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Scroll indicator -->
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
        <button 
          @click="scrollToSection('about')"
          class="flex flex-col items-center text-gray-400 hover:text-blue-600 transition-colors"
          aria-label="Scroll down"
        >
          <span class="text-sm mb-2">Découvrir</span>
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
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
  animation: fade-in-delay 1s ease-out 0.2s both;
}

.animate-spin-slow {
  animation: spin-slow 20s linear infinite;
}

.animate-bounce-slow {
  animation: bounce-slow 3s ease-in-out infinite;
}
</style>

