<script setup lang="ts">
import ContactCard from './ContactCard.vue'

const contacts = [
  {
    id: 1,
    platform: 'Email',
    icon: '📧',
    value: 'mahmoudi.othmane@gmail.com',
    link: 'https://mail.google.com/mail/u/0/#inbox?compose=new',
    bgImage: 'https://images.unsplash.com/photo-1596526131083-e8c633c948d2?w=800'
  },
  {
    id: 2,
    platform: 'LinkedIn',
    icon: '💼',
    value: '@othmane-dev',
    link: 'https://linkedin.com/in/othmane',
    bgImage: 'https://images.unsplash.com/photo-1611944212129-29977ae1398c?w=800'
  },
  {
    id: 3,
    platform: 'GitHub',
    icon: '🐙',
    value: '@othmane',
    link: 'https://github.com/othmane',
    bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800'
  },
  {
    id: 5,
    platform: 'WhatsApp',
    icon: '💬',
    value: '+33 6 12 34 56 78',
    link: 'https://wa.me/33612345678',
    bgImage: 'https://images.unsplash.com/photo-1611746872915-64382b5c76da?w=800'
  }
]
</script>

<template>
  <section id="contact" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">
    <div class="text-center mb-12">
      <h2 class="text-4xl font-bold text-[#CFAF71] mb-4">Me Contacter</h2>
      <p class="text-lg text-[#2A2A2A]/70">Restons en contact ! Choisissez votre plateforme préférée</p>
    </div>
    
    <div class="flex flex-wrap justify-center gap-8 w-full max-w-7xl">
      <ContactCard
        v-for="contact in contacts"
        :key="contact.id"
        :platform="contact.platform"
        :icon="contact.icon"
        :value="contact.value"
        :link="contact.link"
        :bgImage="contact.bgImage"
      />
    </div>
  </section>
</template>