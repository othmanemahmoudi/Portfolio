<script setup lang="ts">
import { ref } from 'vue'

const contacts = [
  {
    id: 1,
    platform: 'Email',
    icon: '📧',
    value: 'mahmoudi.othmane@gmail.com',
    link: 'mailto:mahmoudi.othmane@gmail.com',
    color: 'from-pink-500 to-red-500'
  },
  {
    id: 2,
    platform: 'LinkedIn',
    icon: '💼',
    value: '@othmane-dev',
    link: 'https://linkedin.com/in/othmane',
    color: 'from-blue-500 to-cyan-500'
  },
  {
    id: 3,
    platform: 'GitHub',
    icon: '🐙',
    value: '@othmane',
    link: 'https://github.com/othmane',
    color: 'from-gray-700 to-purple-700'
  },
  {
    id: 4,
    platform: 'WhatsApp',
    icon: '💬',
    value: '+33 6 12 34 56 78',
    link: 'https://wa.me/33612345678',
    color: 'from-green-500 to-emerald-500'
  }
]

const activeContact = ref(null)
</script>

<template>
  <section id="contact" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">
    <h2 class="text-4xl font-bold text-[#CFAF71] mb-12">Me Contacter</h2>

    <!-- Ligne entière -->
    <div
      class="w-full max-w-5xl h-56 rounded-full overflow-hidden shadow-lg relative flex items-center justify-center transition-all duration-700 ease-in-out"
      :class="activeContact ? `bg-gradient-to-br ${activeContact.color}` : 'bg-white'"
      @mouseleave="activeContact = null"
    >
      <!-- État initial : 4 ronds -->
      <div v-if="!activeContact" class="flex w-full h-full justify-around items-center transition-opacity duration-700 ease-in-out opacity-100">
        <div
          v-for="contact in contacts"
          :key="contact.id"
          class="w-24 h-24 rounded-full flex items-center justify-center text-white cursor-pointer bg-gradient-to-br from-gray-700 to-gray-900 hover:scale-110 transition-transform duration-500"
          @mouseenter="activeContact = contact"
        >
          <span class="text-3xl">{{ contact.icon }}</span>
        </div>
      </div>

      <!-- État actif : contact en grand -->
      <transition name="fade" mode="out-in">
        <div
          v-if="activeContact"
          key="active"
          class="absolute inset-0 flex flex-col items-center justify-center text-white text-center px-6 transition-opacity duration-700 ease-in-out"
        >
          <a :href="activeContact.link" target="_blank" class="flex flex-col items-center">
            <span class="text-6xl mb-4 animate-pulse">{{ activeContact.icon }}</span>
            <h3 class="text-2xl font-bold">{{ activeContact.platform }}</h3>
            <p class="mt-2 text-lg">{{ activeContact.value }}</p>
          </a>
        </div>
      </transition>
    </div>
  </section>
</template>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
  transform: scale(0.9);
}
</style>
