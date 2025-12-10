<script setup lang="ts">
import { ref } from 'vue'
import ProjectModal from './ProjectModal.vue'

// Props
const props = defineProps({
  title: { type: String, default: "Title" },
  description: { type: String, default: "Description" },
  details: { type: String, default: "Details" },
  status: { type: String, default: "Status" },
  date: { type: String, default: "Date" },
  company: { type: String, default: "Company" },
  missions: { type: Array<string>, default: () => [] },
  results: { type: Array<string>, default: () => [] },
  technologies: { type: Array<string>, default: () => [] },
  team: { type: String, default: "Team" },
  link: { type: String, default: "Link" }
})

const isModalOpen = ref(false)
const openModal = () => { isModalOpen.value = true }
</script>

<template>
  <div
    class="w-full sm:w-[80%] lg:w-[70%] bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 dark:from-[#CFAF71]/10 dark:via-[#8B6937]/5 dark:to-[#2A2A2A]/20 rounded-xl sm:rounded-2xl shadow-lg overflow-hidden cursor-pointer transform transition duration-500 hover:scale-105 hover:shadow-2xl animate-slideUp border border-[#CFAF71]/40 dark:border-[#CFAF71]/20"
    @click="openModal"
  >
    <div class="p-4 sm:p-6 h-full w-full flex flex-col justify-between">
      <div>
        <h3 class="text-lg sm:text-xl font-bold mb-2 text-[#2A2A2A] dark:text-white line-clamp-2">{{ title }}</h3>
        <p class="text-gray-700 dark:text-gray-400 mb-4 line-clamp-3 text-sm sm:text-base">{{ description }}</p>
      </div>

      <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2 sm:gap-0 text-xs sm:text-sm text-[#2A2A2A]/80 dark:text-gray-400 mt-auto">
        <span class="px-3 py-1 bg-[#CFAF71]/20 dark:bg-[#CFAF71]/10 rounded-full truncate">{{ company }}</span>
        <span class="flex-shrink-0">{{ date }}</span>
      </div>
    </div>
  </div>

  <!-- Modal -->
  <ProjectModal
    v-if="isModalOpen"
    :title="props.title"
    :description="props.description"
    :details="props.details"
    :status="props.status"
    :date="props.date"
    :company="props.company"
    :missions="props.missions"
    :results="props.results"
    :technologies="props.technologies"
    :team="props.team"
    :link="props.link"
    @close="isModalOpen = false"
  />
</template>

<style scoped>
@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slideUp {
  animation: slideUp 0.6s ease-out forwards;
}

.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>