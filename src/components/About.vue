<script setup lang="ts">
import { ref, onMounted } from 'vue'

const terminalText = ref('')
const showCursor = ref(true)
const isTypingComplete = ref(false)

const fullText = `Développeur Python Full Stack, je possède une expérience dans la conception, le développement et l’optimisation de solutions web modernes. Mon parcours m’a permis de travailler sur des projets variés, allant de plateformes SaaS omnicanales à des applications spécialisées en génération de contenu et en interfaces innovantes. Passionné par le code et animé par la volonté de résoudre des problèmes complexes, je combine expertise technique, créativité et rigueur pour livrer des solutions robustes, performantes et adaptées aux besoins des utilisateurs.

🎯 Mon approche
Polyvalence technique : maîtrise des environnements backend (Python, Django, Flask, microservices, API REST sécurisées) et frontend (Vue.js, TailwindCSS, TypeScript).

Culture DevOps : expérience en CI/CD, Docker, Kubernetes, monitoring et automatisation pour garantir la fiabilité et la scalabilité des systèmes.

Esprit collaboratif : habitué à travailler en synergie avec des équipes R&D, produit et design, afin d’assurer des mises à jour continues et une qualité optimale.

Orientation solution : capacité à transformer des besoins métiers en fonctionnalités concrètes, sécurisées et performantes.

🔑 Ce qui me distingue
Une passion constante pour le code et l’innovation.

Une capacité à allier performance technique et sens de l’expérience utilisateur.

Une volonté d’amélioration continue et d’apprentissage permanent.`

onMounted(() => {
  let index = 0
  const typingSpeed = 5 // millisecondes par caractère
  
  const typeText = () => {
    if (index < fullText.length) {
      terminalText.value += fullText[index]
      index++
      setTimeout(typeText, typingSpeed)
    } else {
      isTypingComplete.value = true
    }
  }
  
  // Démarrer l'animation après un court délai
  setTimeout(typeText, 500)
  
  // Animation du curseur clignotant
  setInterval(() => {
    showCursor.value = !showCursor.value
  }, 500)
})
</script>

<template>
  <section id="about" class=" flex flex-col items-center justify-center py-20">
    <h2 class="text-4xl font-bold text-[#CFAF71] mb-12">Profile</h2>
      <div class="terminal rounded-lg font-mono  w-[85%] mx-auto shadow-2xl"> 
    <!-- Header du terminal -->
    <div class="terminal-header bg-[#2A2A2A] text-white p-3 rounded-t-lg flex items-center">
      <span class="text-red-500 text-4xl leading-[0px] align-middle -mt-2">•</span>
      <span class="text-yellow-500 text-4xl leading-[0px] align-middle -mt-2 ml-1">•</span>
      <span class="text-green-500 text-4xl leading-[0px] align-middle -mt-2 ml-1">•</span>
      <span class="ml-4 text-sm text-gray-300 font-semibold">portfolio.py --- Python 3.11</span>
    </div>
    
    <!-- Corps du terminal -->
    <div class="bg-[#1e1e1e] text-gray-100 p-6 rounded-b-lg min-h-[300px]">
      <div class="mb-4">
        <span class="text-[#CFAF71]">othmane@portfolio</span>
        <span class="text-gray-400">:</span>
        <span class="text-blue-400">~</span>
        <span class="text-gray-400">$</span>
        <span class="text-green-400 ml-2">cat profil.txt</span>
      </div>
      
      <div class="text-gray-300 leading-relaxed whitespace-pre-wrap">
        {{ terminalText }}<span v-if="showCursor" class="text-[#CFAF71] animate-pulse">█</span>
      </div>
      
      <div v-if="isTypingComplete" class="mt-6 flex items-center">
        <span class="text-[#CFAF71]">othmane@portfolio</span>
        <span class="text-gray-400">:</span>
        <span class="text-blue-400">~</span>
        <span class="text-gray-400">$</span>
        <span class="text-[#CFAF71] ml-2 animate-pulse">█</span>
      </div>
    </div>
  </div>
  </section>

</template>

<style scoped>
.terminal {
  border: 1px solid #333;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}

.animate-pulse {
  animation: pulse 1s ease-in-out infinite;
}
</style>