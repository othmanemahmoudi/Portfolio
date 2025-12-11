<script setup lang="ts">
import HobieCard from './HobieCard.vue'
import BannerImage from './BannerImage.vue'

// Import des images locales
import h1 from '../assets/hobies/h1.jpeg'
import h2 from '../assets/hobies/h2.jpeg'
import h3 from '../assets/hobies/h3.jpeg'
import h4 from '../assets/hobies/h4.jpeg'
import h5 from '../assets/hobies/h5.jpeg'
import h6 from '../assets/hobies/h6.jpeg'
import h7 from '../assets/hobies/h7.jpeg'
import h8 from '../assets/hobies/h8.jpeg'

const hobies = [
  {
    id: 2,
    name: 'Voyage',
    icon: '✈️',
    bgImage: 'https://images.unsplash.com/photo-1504150558240-0b4fd8946624?w=800'
  },
  {
    id: 3,
    name: 'Lecture',
    icon: '📚',
    bgImage: 'https://images.unsplash.com/photo-1580121441575-41bcb5c6b47c?q=800'
  },
  {
    id: 4,
    name: 'Sports collectifs',
    icon: '⚽',
    bgImage: 'https://images.unsplash.com/photo-1546608235-3310a2494cdf?w=800'
  },
    {
    id: 6,
    name: 'Sports individuels',
    icon: '🏋️',
    bgImage: 'https://images.unsplash.com/photo-1565992441121-4367c2967103?w=800'
  },
  {
    id: 5,
    name: 'Coding Game',
    icon: '🎮',
    bgImage: 'https://images.unsplash.com/photo-1511512578047-dfb367046420?w=800'
  }
]

// Images extraites automatiquement pour le banner
const hobiesImages = [
  h4,
  h2,
  h1,
  h3,
  h5,
  h6,
  h7,
  h8
]
</script>

<template>
  <section id="hobies" class=" flex flex-col items-center justify-center px-4">
    <div class="text-center my-12">
      <h2 class="text-4xl font-bold text-[#CFAF71] mb-4">Loisirs</h2>
      <p class="text-lg text-[#CFAF71]">Ce que j'aime faire en dehors du développement</p>
    </div>

    <div class="flex flex-wrap justify-center gap-6 w-full max-w-6xl">
      <HobieCard
        v-for="hobie in hobies"
        :key="hobie.id"
        :name="hobie.name"
        :icon="hobie.icon"
        :bgImage="hobie.bgImage"
      />
      <BannerImage :images="hobiesImages" />
    </div>
  </section>
</template>