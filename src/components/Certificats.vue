<script setup lang="ts">
import CertificationCard from './CertificationCard.vue'

const certifications = [
  {
    id: 1,
    title: 'AWS Certified Solutions Architect',
    subtitle: 'Amazon Web Services',
    description: 'Certification professionnelle démontrant une expertise dans la conception de systèmes distribués sur AWS.',
    date: 'Janvier 2024 - Présent',
    tags: ['AWS', 'Cloud', 'Architecture'],
    certificateUrl: 'https://exemple.com/cert1'
  },
  {
    id: 2,
    title: 'Vue.js 3 Master Certification',
    subtitle: 'Vue School',
    description: 'Maîtrise avancée du framework Vue.js 3 incluant Composition API, Pinia et Vue Router.',
    date: 'Mars 2024',
    tags: ['Vue.js', 'Frontend', 'JavaScript'],
    certificateUrl: 'https://exemple.com/cert2'
  },
  {
    id: 3,
    title: 'Professional Scrum Master I',
    subtitle: 'Scrum.org',
    description: 'Certification en méthodologie Agile et gestion de projets avec le framework Scrum.',
    date: 'Juin 2023',
    tags: ['Agile', 'Scrum', 'Project Management'],
    certificateUrl: 'https://exemple.com/cert3'
  },
  {
    id: 4,
    title: 'Docker Certified Associate',
    subtitle: 'Docker Inc.',
    description: 'Compétences avancées en conteneurisation et déploiement d\'applications avec Docker.',
    date: 'Septembre 2023',
    tags: ['Docker', 'DevOps', 'Containers'],
    certificateUrl: 'https://exemple.com/cert4'
  }
]
</script>

<template>
  <section id="certificats" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">
    <h2 class="text-4xl font-bold text-[#CFAF71] mb-12">Mes Certifications</h2>
    
    <div class="flex flex-wrap justify-center gap-8 w-full max-w-7xl">
      <div class="w-full md:w-[48%] lg:w-[48%]" v-for="cert in certifications" :key="cert.id">
        <CertificationCard
          :title="cert.title"
          :subtitle="cert.subtitle"
          :description="cert.description"
          :date="cert.date"
          :tags="cert.tags"
          :certificateUrl="cert.certificateUrl"
        />
      </div>
    </div>
  </section>
</template>