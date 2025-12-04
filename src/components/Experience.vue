<script setup lang="ts">
import ProjectCard from './ProjectCard.vue';

const projects = [
  {
    id: 1,
    title: 'Projet E-commerce',
    description: 'Une plateforme de vente en ligne complète avec panier, paiement et gestion des stocks.',
    status: 'Terminé',
    date: '2024'
  },
  {
    id: 2,
    title: 'Application Mobile',
    description: 'Application de suivi fitness avec tracking des performances et objectifs personnalisés.',
    status: 'En cours',
    date: '2024'
  },
  {
    id: 3,
    title: 'Dashboard Analytics',
    description: 'Tableau de bord analytique en temps réel avec visualisation de données complexes.',
    status: 'Terminé',
    date: '2023'
  }
];
</script>

<template>
  <section id="experience" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">
    <h2 class="text-4xl font-bold text-[#CFAF71] mb-12">Expériences professionnelles</h2>
    
    <div class="flex flex-wrap justify-center gap-6 w-full max-w-7xl">
      <ProjectCard 
        v-for="project in projects" 
        :key="project.id"
        :title="project.title"
        :description="project.description"
        :status="project.status"
        :date="project.date"
      />
    </div>
  </section>
</template>