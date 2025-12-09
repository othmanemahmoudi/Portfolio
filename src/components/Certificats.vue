<script setup lang="ts">
import CertificationCard from './CertificationCard.vue'

const certifications = [
    {
    id: 1,
    title: 'Python for Data Science, AI & Development',
    subtitle: 'IBM',
    description: 'Maîtrise complète Pandas et NumPy, travail sous Jupyter Notebook et extraction de données via APIs et web scraping.',
    date: 'octobre 2022',
    tags: ['Data Analysis', 'Data Processing', 'Data Manipulation'],
    certificateUrl: 'https://www.coursera.org/account/accomplishments/verify/UW9FWM6RVPHK'
  },
  {
    id: 2,
    title: 'Gestion de projet Agile',
    subtitle: 'Google',
    description: 'Maîtrise avancée de la gestion de projet Agile avec le cadre Scrum, incluant valeurs, piliers, événements clés et accompagnement des équipes.',
    date: 'décembre 2022',
    tags: ['Agile Methodology', 'Sprint Planning', 'Team Management'],
    certificateUrl: 'https://www.coursera.org/account/accomplishments/verify/T92C2M4RZHGL'
  },
  {
    id: 4,
    title: 'Tosa Python 3',
    subtitle: 'Tosa',
    description: 'Vérifier le score avec le code: 2023-231913929-101, le score: 783/1000.',
    date: 'Mars 2023',
    tags: ['Python'],
    certificateUrl: 'https://www.tosa.org/FR/index#'
  },
    {
    id: 3,
    title: 'Python Packages for Data Science',
    subtitle: 'University of Colorado Boulder',
    description: 'Maîtrise des principaux outils pour la data science, incluant manipulation de données et visualisations avancées avec Matplotlib et Seaborn.',
    date: 'Juin 2023',
    tags: ['Matplotlib', 'Seaborn', 'Plot (Graphics)', 'Data Visualization'],
    certificateUrl: 'https://www.coursera.org/account/accomplishments/verify/CGDRPZAKWSWC'
  },
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