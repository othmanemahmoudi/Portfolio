<script setup lang="ts">
import { ref } from 'vue'

const isDownloading = ref(false)

const showMessage = () => {
  isDownloading.value = true

  setTimeout(() => {
    isDownloading.value = false
  }, 2000)
}


const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    const headerHeight = 60 // Hauteur approximative du header
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
  <header class=" backdrop-blur-md shadow-sm bg-black w-full  ">
    <nav class="container mx-auto px-3 py-3 h-[100%] ">
      <div class="flex items-center justify-between">
        <!-- Logo -->
        <div class="flex items-center">
          <a href="#" @click.prevent="scrollToSection('hero')" class="dark:text-[#FFFFFF] text-2xl font-bold text-white hover:text-[#CFAF71] transition-colors">
            Portfolio
          </a>
        </div>

        <div class="flex flex-col items-end mr-4">
          
          <!-- Message -->
          <p 
            v-if="isDownloading"
            class="text-[#CFAF71] font-semibold text-sm transition-opacity duration-500"
          >
            En cours ...
          </p>

          <!-- Lien CV -->
          <a 
            v-else
            href="/CV.pdf" 
            download="CV_Othmane_Mahmoudi.pdf"
            @click="showMessage()"
            class="text-white hover:text-[#CFAF71] font-medium"
          >
            Télécharger mon CV
          </a>

        </div>


        <!-- Desktop Navigation -->
        <div class="desktop-nav">
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
            href="#formations" 
            @click.prevent="scrollToSection('formations')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Formations
          </a>
                    <a 
            href="#certificats" 
            @click.prevent="scrollToSection('certificats')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Certifications
          </a>
          <a 
            href="#skills" 
            @click.prevent="scrollToSection('skills')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Compétences
          </a>
          <a 
            href="#languages" 
            @click.prevent="scrollToSection('languages')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Langages
          </a>

                    <a 
            href="#hobies" 
            @click.prevent="scrollToSection('hobies')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium"
          >
            Loisirs
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
          class="mobile-nav p-2 rounded-md text-white hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-blue-500"
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
        class="md:hidden h-[100%] mt-2 pb-2 border-t border-gray-200"
      >
        <div class="flex flex-col space-y-3 pt-3">
          <a 
            href="#hero" 
            @click.prevent="scrollToSection('hero')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            Accueil
          </a>
          <a 
            href="#about" 
            @click.prevent="scrollToSection('about')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            À propos
          </a>
          <a 
            href="#experience" 
            @click.prevent="scrollToSection('experience')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            Expérience
          </a>
                              <a 
            href="#formations" 
            @click.prevent="scrollToSection('formations')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium py-2"
          >
            Formations
          </a>
                              <a 
            href="#certificats" 
            @click.prevent="scrollToSection('certificats')" 
            class="text-white hover:text-[#CFAF71] transition-colors font-medium py-2"
          >
            Certifications
          </a>
                    <a 
            href="#skills" 
            @click.prevent="scrollToSection('skills')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            Compétences
          </a>
          <a 
            href="#languages" 
            @click.prevent="scrollToSection('languages')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            Langages
          </a>
                    <a 
            href="#hobies" 
            @click.prevent="scrollToSection('hobies')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            Loisirs
          </a>
          <a 
            href="#contact" 
            @click.prevent="scrollToSection('contact')" 
            class="text-white hover:text-blue-600 transition-colors font-medium py-2"
          >
            Contact
          </a>

        </div>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.desktop-nav {
  display: none;
  align-items: center;
  gap: 2rem; /* équivalent à space-x-8, mais attention: space-x-8 ajoute un margin-left à chaque enfant sauf le premier, donc on peut utiliser gap si on passe à une flexbox avec gap */
}

@media (min-width: 1300px) { 
  .desktop-nav {
    display: flex;
  }
}

.mobile-nav {
  display: none;
  align-items: center;
  gap: 2rem
}

@media (max-width: 1299px) { 
  .mobile-nav {
    display: flex;
  }
}
</style>

