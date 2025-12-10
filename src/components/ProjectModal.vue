<template>
  <div
    class="fixed inset-0 bg-black/60 flex items-center justify-center z-50 p-4 backdrop-blur-sm animate-fadeInModal"
    @click.self="$emit('close')"
  >
    <div class="bg-white rounded-2xl shadow-2xl w-full max-w-[95vw] h-full max-h-[90vh] sm:w-[85%] sm:h-[85%] flex flex-col relative border border-[#CFAF71]/30 overflow-hidden">

      <!-- Header -->
      <div class="flex items-center justify-between py-4 px-4 sm:px-6 border-b border-[#CFAF71]/20 bg-gradient-to-r from-[#CFAF71]/10 to-[#8B6937]/10">
        <h2 class="text-lg sm:text-2xl font-bold text-[#2A2A2A]">{{ title }}</h2>
        <button
          class="text-[#CFAF71] hover:text-[#8B6937] transition-colors duration-200 w-8 h-8 flex items-center justify-center rounded-full hover:bg-[#CFAF71]/10 cursor-pointer"
          @click="$emit('close')"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>

      <!-- Scrollable content -->
      <div class="flex-1 overflow-y-auto px-4 sm:px-6 py-6 custom-scrollbar">
        <!-- Contexte -->
        <div class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3">Contexte du projet</h3>
          <p class="text-[#2A2A2A]/80 text-base leading-relaxed whitespace-pre-line">{{ details }}</p>
        </div>

        <!-- Missions -->
        <div v-if="missions?.length" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3">Missions et responsabilités</h3>
          <ul class="space-y-2">
            <li v-for="(mission, index) in missions" :key="index" class="flex items-start gap-3 text-[#2A2A2A]/80">
              <span class="w-6 h-6 rounded-full bg-gradient-to-r from-[#CFAF71] to-[#8B6937] flex items-center justify-center text-white text-xs font-bold mt-0.5">
                {{ index + 1 }}
              </span>
              <span class="flex-1">{{ mission }}</span>
            </li>
          </ul>
        </div>

        <!-- Résultats -->
        <div v-if="results?.length" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3">Résultats et réalisations</h3>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div v-for="(result, index) in results" :key="index" class="p-4 bg-gradient-to-br from-[#CFAF71]/5 to-[#8B6937]/5 rounded-xl border border-[#CFAF71]/20 hover:border-[#CFAF71]/40 transition-all">
              <p class="text-[#2A2A2A]/80 text-sm">{{ result }}</p>
            </div>
          </div>
        </div>

        <!-- Technologies -->
        <div v-if="technologies?.length" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3">Technologies utilisées</h3>
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

        <!-- Équipe -->
        <div v-if="team" class="mb-8">
          <h3 class="text-xl font-bold text-[#CFAF71] mb-3">Équipe</h3>
          <p class="text-[#2A2A2A]/80">{{ team }}</p>
        </div>

        <!-- Lien -->
        <div v-if="link && link !== '#'" class="mb-4">
          <a
            :href="link"
            target="_blank"
            class="inline-flex items-center gap-2 px-6 py-3 bg-gradient-to-r from-[#CFAF71] to-[#8B6937] text-white rounded-lg font-semibold hover:opacity-90 transition-opacity shadow-lg"
          >
            Voir le projet
          </a>
        </div>
      </div>

      <!-- Footer -->
      <div class="flex-shrink-0 p-2 bg-gradient-to-r from-[#CFAF71]/5 to-[#8B6937]/5 backdrop-blur-sm flex justify-end border-t border-[#CFAF71]/20">
        <button
          @click="$emit('close')"
          class="bg-gradient-to-r from-[#2A2A2A] to-[#1A1A1A] text-[#CFAF71] font-semibold py-3 px-8 rounded-lg hover:opacity-90 transition-opacity shadow-md"
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
  details: String,
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
</style>
