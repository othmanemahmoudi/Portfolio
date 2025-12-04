<script setup lang="ts">
import { ref } from 'vue'
import ProjectModal from './ProjectModal.vue'

// Props
defineProps({
  title: { type: String, default: "Mon projet génial" },
  description: { type: String, default: "Voici une description rapide du projet." },
  status: { type: String, default: "En cours" },
  date: { type: String, default: "Décembre 2025" }
})

const isModalOpen = ref(false)
const openModal = () => { isModalOpen.value = true }
</script>

<template>
  <div
    class="w-full sm:w-[48%] lg:w-[30%] aspect-[4/5] bg-gradient-to-br from-[#CFAF71]/20 via-[#FFECC2]/20 to-[#8B6937]/20 rounded-2xl shadow-lg overflow-hidden cursor-pointer transform transition duration-500 hover:scale-105 hover:shadow-2xl animate-slideUp border border-[#CFAF71]/40"
    @click="openModal"
  >
    <div class="p-6 h-full flex flex-col justify-between">
      <div>
        <h3 class="text-xl font-bold mb-2 text-[#2A2A2A]">{{ title }}</h3>
        <p class="text-gray-700 mb-4 line-clamp-3">{{ description }}</p>
      </div>
      
      <div class="flex justify-between items-center text-sm text-[#2A2A2A]/80 mt-auto">
        <span class="px-3 py-1 bg-[#CFAF71]/20 rounded-full">{{ status }}</span>
        <span>{{ date }}</span>
      </div>
    </div>
  </div>

  <!-- Modal -->
  <ProjectModal
    v-if="isModalOpen"
    :title="title"
    :description="description"
    :status="status"
    :date="date"
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