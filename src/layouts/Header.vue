<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    const headerHeight = 80 // Hauteur approximative du header
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - headerHeight

    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
    isMenuOpen.value = false
  }
}
</script>

<template>
  <header class="fixed top-0 left-0 right-0 z-50 backdrop-blur-md shadow-sm bg-black">
    <nav class="container mx-auto px-4 py-4 ">
      <div class="flex items-center justify-between">
        <!-- Logo -->
        <div class="flex items-center">
          <a href="#" @click.prevent="scrollToSection('hero')" class="text-2xl font-bold text-white hover:text-[#CFAF71] transition-colors">
            Portfolio
          </a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <a 
            href="#hero" 
            @click.prevent="scrollToSection('hero')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Accueil
          </a>
          <a 
            href="#about" 
            @click.prevent="scrollToSection('about')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            À propos
          </a>
          <a 
            href="#experience" 
            @click.prevent="scrollToSection('experience')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Expérience
          </a>
          <a 
            href="#projects" 
            @click.prevent="scrollToSection('projects')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Projets
          </a>
          <a 
            href="#skills" 
            @click.prevent="scrollToSection('skills')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Compétences
          </a>
          <a 
            href="#contact" 
            @click.prevent="scrollToSection('contact')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Contact
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <button 
          @click="toggleMenu" 
          class="md:hidden p-2 rounded-md text-gray-700 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-blue-500"
          aria-label="Toggle menu"
        >
          <svg 
            v-if="!isMenuOpen" 
            class="w-6 h-6" 
            fill="none" 
            stroke="currentColor" 
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <svg 
            v-else 
            class="w-6 h-6" 
            fill="none" 
            stroke="currentColor" 
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <!-- Mobile Navigation -->
      <div 
        v-show="isMenuOpen" 
        class="md:hidden mt-4 pb-4 border-t border-gray-200"
      >
        <div class="flex flex-col space-y-3 pt-4">
          <a 
            href="#hero" 
            @click.prevent="scrollToSection('hero')" 
            class="text-gray-700 hover:text-blue-600 transition-colors font-medium py-2"
          >
            Accueil
          </a>
          <a 
            href="#about" 
            @click.prevent="scrollToSection('about')" 
            class="text-gray-700 hover:text-blue-600 transition-colors font-medium py-2"
          >
            À propos
          </a>
          <a 
            href="#experience" 
            @click.prevent="scrollToSection('experience')" 
            class="text-gray-700 hover:text-blue-600 transition-colors font-medium py-2"
          >
            Expérience
          </a>
          <a 
            href="#projects" 
            @click.prevent="scrollToSection('projects')" 
            class="text-gray-700 hover:text-blue-600 transition-colors font-medium py-2"
          >
            Projets
          </a>
          <a 
            href="#skills" 
            @click.prevent="scrollToSection('skills')" 
            class="text-gray-700 hover:text-blue-600 transition-colors font-medium py-2"
          >
            Compétences
          </a>
          <a 
            href="#contact" 
            @click.prevent="scrollToSection('contact')" 
            class="text-gray-700 hover:text-blue-600 transition-colors font-medium py-2"
          >
            Contact
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>

<style scoped>
/* Styles supplémentaires si nécessaire */
</style>

