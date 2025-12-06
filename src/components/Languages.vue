<script setup lang="ts">
import LanguageCard from './LanguageCard.vue'

const languages = [
  {
    id: 1,
    language: 'Français',
    flag: '🇫🇷',
    level: 'Langue maternelle'
  },
  {
    id: 2,
    language: 'Arabe',
    flag: '🇲🇦',
    level: 'Langue maternelle'
  },
  {
    id: 3,
    language: 'Anglais',
    flag: '🇬🇧',
    level: 'Avancé (C1)'
  }
]
</script>

<template>
  <section id="languages" class=" flex flex-col items-center justify-center">
    <div class="text-center mb-12">
      <h2 class="text-4xl font-bold text-[#CFAF71] mb-4">Langues</h2>
      <p class="text-lg text-[#2A2A2A]/70">Communication internationale</p>
    </div>
    
    <div class="flex flex-wrap justify-center gap-8 w-full max-w-7xl">
      <LanguageCard
        v-for="lang in languages"
        :key="lang.id"
        :language="lang.language"
        :flag="lang.flag"
        :level="lang.level"
      />
    </div>
  </section>
</template>