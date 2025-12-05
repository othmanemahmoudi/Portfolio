<script setup lang="ts">
import HobieCard from './HobieCard.vue'
import BannerImage from './BannerImage.vue'

const hobies = [
  {
    id: 1,
    name: 'Musique',
    icon: '🎵',
    bgImage: 'https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?w=800'
  },
  {
    id: 2,
    name: 'Voyage',
    icon: '✈️',
    bgImage: 'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=800'
  },
  {
    id: 3,
    name: 'Lecture',
    icon: '📚',
    bgImage: 'https://images.unsplash.com/photo-1512820790803-83ca734da794?w=800'
  },
  {
    id: 4,
    name: 'Sport',
    icon: '🏋️‍♂️',
    bgImage: 'https://images.unsplash.com/photo-1517832207067-4db24a2ae47c?w=800'
  },
  {
    id: 5,
    name: 'Cinéma',
    icon: '🎬',
    bgImage: 'https://images.unsplash.com/photo-1497032205916-ac775f0649ae?w=800'
  }
]

// Images extraites automatiquement pour le banner
const hobiesImages = hobies.map(h => h.bgImage)
</script>

<template>
  <section id="hobies" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">



    <div class="text-center my-12">
      <h2 class="text-4xl font-bold text-[#2A2A2A] mb-4">Loisirs</h2>
      <p class="text-lg text-[#2A2A2A]/70">Ce que j’aime faire en dehors du développement</p>
    </div>

    <div class="flex flex-wrap justify-center gap-6 w-full max-w-6xl">
      <HobieCard
        v-for="hobie in hobies"
        :key="hobie.id"
        :name="hobie.name"
        :icon="hobie.icon"
        :bgImage="hobie.bgImage"
      />
          <!-- Banner -->
    <BannerImage :images="hobiesImages" />
    </div>
    

  </section>
</template>
