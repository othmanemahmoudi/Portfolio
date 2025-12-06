<template>
  <div
    class="fixed inset-0 bg-black/60 flex items-center justify-center z-50 p-4 backdrop-blur-sm"
    @click.self="$emit('close')"
  >
    <div class="bg-white rounded-2xl shadow-2xl w-[90%] max-w-5xl h-[85%] flex flex-col relative animate-fadeInModal border border-[#CFAF71]/30 overflow-hidden">

      <!-- Header fixe -->
      <div class="flex-shrink-0 p-6 pb-4 border-b border-[#CFAF71]/20 bg-gradient-to-r from-[#CFAF71]/10 to-[#8B6937]/10">
        <button
          class="absolute top-4 right-4 text-[#CFAF71] hover:text-[#8B6937] transition-colors duration-200 w-8 h-8 flex items-center justify-center rounded-full hover:bg-[#CFAF71]/10 cursor-pointer z-10"
          @click="$emit('close')"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>

        <div class="pr-10">
          <h2 class="text-3xl font-bold text-[#2A2A2A] mb-3">{{ title }}</h2>
          <div class="flex flex-wrap gap-3 text-sm">
            <span class="px-4 py-1 bg-gradient-to-r from-[#CFAF71] to-[#8B6937] text-white rounded-full font-medium shadow-md">
              {{ status }}
            </span>
            <span class="px-4 py-1 bg-white/80 text-[#2A2A2A] rounded-full font-medium border border-[#CFAF71]/30">
              {{ date }}
            </span>
            <span v-if="company" class="px-4 py-1 bg-white/80 text-[#2A2A2A] rounded-full font-medium border border-[#CFAF71]/30">
              {{ company }}
            </span>
          </div>
        </div>
      </div>

      <!-- Contenu scrollable -->
      <div class="flex-1 overflow-y-auto px-6 py-6 custom-scrollbar">

        <!-- Context / Description -->
        <div class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/>
            </svg>
            Contexte du projet
          </h3>
          <p class="text-[#2A2A2A]/80 text-base leading-relaxed">
            {{ description }}
          </p>
        </div>

        <!-- Missions -->
        <div v-if="missions && missions.length > 0" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2"/>
            </svg>
            Missions et responsabilites
          </h3>
          <ul class="space-y-2">
            <li v-for="(mission, index) in missions" :key="index" class="flex items-start gap-3 text-[#2A2A2A]/80">
              <span class="flex-shrink-0 w-6 h-6 rounded-full bg-gradient-to-r from-[#CFAF71] to-[#8B6937] flex items-center justify-center text-white text-xs font-bold mt-0.5">
                {{ index + 1 }}
              </span>
              <span class="flex-1">{{ mission }}</span>
            </li>
          </ul>
        </div>

        <!-- Resultats -->
        <div v-if="results && results.length > 0" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"/>
            </svg>
            Resultats et realisations
          </h3>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div v-for="(result, index) in results" :key="index" class="p-4 bg-gradient-to-br from-[#CFAF71]/5 to-[#8B6937]/5 rounded-xl border border-[#CFAF71]/20 hover:border-[#CFAF71]/40 transition-all">
              <div class="flex items-start gap-3">
                <svg class="w-5 h-5 text-[#CFAF71] flex-shrink-0 mt-0.5" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"/>
                </svg>
                <p class="text-[#2A2A2A]/80 text-sm">{{ result }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Technologies -->
        <div v-if="technologies && technologies.length > 0" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/>
            </svg>
            Technologies utilisees
          </h3>
          <div class="flex flex-wrap gap-3">
            <span
              v-for="(tech, index) in technologies"
              :key="index"
              class="px-4 py-2 bg-gradient-to-r from-[#2A2A2A] to-[#1A1A1A] text-white rounded-lg text-sm font-medium shadow-md hover:scale-105 transition-transform"
            >
              {{ tech }}
            </span>
          </div>
        </div>

        <!-- Equipe -->
        <div v-if="team" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3 flex items-center gap-2">
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/>
            </svg>
            Equipe
          </h3>
          <p class="text-[#2A2A2A]/80">{{ team }}</p>
        </div>

        <!-- Liens / Actions -->
        <div v-if="link" class="mb-4">
          <a
            :href="link"
            target="_blank"
            class="inline-flex items-center gap-2 px-6 py-3 bg-gradient-to-r from-[#CFAF71] to-[#8B6937] text-white rounded-lg font-semibold hover:opacity-90 transition-opacity shadow-lg"
          >
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"/>
            </svg>
            Voir le projet
          </a>
        </div>

      </div>

      <!-- Footer avec bouton à droite -->
      <div class="flex-shrink-0 p-6 pt-4 bg-gradient-to-r from-[#CFAF71]/5 to-[#8B6937]/5 backdrop-blur-sm flex justify-end border-t border-[#CFAF71]/20">
        <button
          @click="$emit('close')"
          class="bg-gradient-to-r from-[#2A2A2A] to-[#1A1A1A] cursor-pointer text-[#CFAF71] font-semibold py-3 px-8 rounded-lg hover:opacity-90 transition-opacity shadow-md"
        >
          Fermer
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  title: String,
  description: String,
  status: String,
  date: String,
  company: String,
  missions: Array<string>,
  results: Array<string>,
  technologies: Array<string>,
  team: String,
  link: String
})
</script>

<style scoped>
@keyframes fadeInModal {
  from {
    opacity: 0;
    transform: scale(0.95) translateY(-20px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

.animate-fadeInModal {
  animation: fadeInModal 0.3s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}

/* Scrollbar personnalisée */
.custom-scrollbar {
  scrollbar-width: thin;
  scrollbar-color: #CFAF71 transparent;
}

.custom-scrollbar::-webkit-scrollbar {
  width: 6px;
}

.custom-scrollbar::-webkit-scrollbar-track {
  background: transparent;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
  background: #CFAF71;
  border-radius: 3px;
  transition: background 0.2s;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
  background: #b8955a;
}
</style>