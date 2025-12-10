<script setup lang="ts">
import { ref } from 'vue'

interface Contact {
  id: number
  platform: string
  icon: string
  value: string
  link: string
  bgImage?: string
}

const contacts = ref<Contact[]>([
  {
    id: 1,
    platform: 'Email',
    icon: '📧',
    value: 'mahmoudi.othmane1@gmail.com',
    link: 'https://mail.google.com/mail/u/0/#inbox?compose=new',
    bgImage: 'https://images.unsplash.com/photo-1596526131083-e8c633c948d2?w=800'
  },
  {
    id: 2,
    platform: 'LinkedIn',
    icon: '💼',
    value: '@mahmoudi-othmane',
    link: 'https://www.linkedin.com/in/mahmoudi-othmane',
    bgImage: 'https://images.unsplash.com/photo-1611944212129-29977ae1398c?w=800'
  },
  {
    id: 3,
    platform: 'GitHub',
    icon: '🐙',
    value: '@othmanemahmoudi',
    link: 'https://github.com/othmanemahmoudi',
    bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800'
  },
  {
    id: 4,
    platform: 'WhatsApp',
    icon: '💬',
    value: '+33 6 99 86 14 96',
    link: 'https://web.whatsapp.com',
    bgImage: 'https://images.unsplash.com/photo-1611746872915-64382b5c76da?w=800'
  },
])

const activeContact = ref<Contact | null>(null)
</script>

<template>
  <section id="contact" class=" flex flex-col items-center justify-center py-20 px-4">
    <h2 class="text-4xl font-bold text-[#CFAF71] mb-6">Me Contacter</h2>

    <!-- Ligne entière -->
    <div
      class="w-full max-w-5xl h-56 rounded-full overflow-hidden shadow-lg relative flex items-center justify-center transition-all duration-1000 ease-in-out"
      :style="activeContact ? { backgroundImage: `url(${activeContact.bgImage})`, backgroundSize: 'cover', backgroundPosition: 'center' } : { backgroundColor: '#fff' }"
      @mouseleave="activeContact = null"
    >
      <!-- État initial : 4 ronds -->
      <div v-if="!activeContact" class="flex w-full h-full justify-around items-center transition-opacity duration-700 ease-in-out opacity-100">
        <div
          v-for="contact in contacts"
          :key="contact.id"
          class="w-24 h-24 rounded-full flex items-center justify-center text-white cursor-pointer hover:scale-110 transition-transform duration-500"
          :style="{ backgroundImage: `url(${contact.bgImage})`, backgroundSize: 'cover', backgroundPosition: 'center' }"
          @mouseenter="activeContact = contact"
        >
        </div>
      </div>

      <!-- État actif : contact en grand -->
      <transition>
        <div
          v-if="activeContact"
          key="active"
          class="absolute inset-0 flex flex-col items-center justify-center text-white text-center px-6 bg-black/50"
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
