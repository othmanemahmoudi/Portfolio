<script setup lang="ts">
import ProjectCard from './ProjectCard.vue';

const projects = [

  {
  id: 1,
  title: 'Développeur Python Full Stack – Plateforme SaaS Retail Omnicanale',
  description:'Développement full stack sur la plateforme SaaS OneStock, basée sur une architecture microservices à haute disponibilité. Contribution au backend (Python/Flask) et au frontend (Vue.js / TypeScript) pour améliorer les performances, la scalabilité et l’expérience utilisateur.',
  details: `OneStock est une solution SaaS omnicanale utilisée par des retailers internationaux : Mano Mano, Yves Rocher, Intersport, Orchestra…
  La plateforme gère des millions d’événements par jour : gestion des stocks, commandes, promotions, orchestration logistique…
  J’ai travaillé sur des services critiques, optimisés pour gérer les pics de charge (Black Friday, Soldes), tout en renforçant la sécurité, la fiabilité et la scalabilité.`,
  status: 'En cours',
  date: 'Octobre 2023 – Présent',
  company: 'OneStock',
  missions: [
    'Développement backend Python/Flask : microservices, endpoints sécurisés, calculs métiers, orchestration des données (MongoDB, Redis).',
    'Optimisation de services critiques (stocks, promotions, règles métiers) utilisés en temps réel par des milliers d’utilisateurs.',
    'Conception d’interfaces frontend modernes avec Vue 3, TypeScript, Pinia, TailwindCSS et Storybook.',
    'Intégration de moteurs de promotion, connecteurs CRM et systèmes externes via API REST sécurisées.',
    'Mise en place ou amélioration de pipelines CI/CD (GitLab, Docker, Kubernetes).',
    'Monitoring applicatif : logs structurés, alerting, dashboards, suivi de performance.',
    'Pratiques de qualité : revues de code, tests unitaires/integ, documentation Confluence.'
  ],
  results: [
    '⏱️ Réduction de ~2% du temps de réponse sur des services critiques utilisés quotidiennement à grande échelle.',
    '📦 Amélioration de la fiabilité durant les pics de charge (Black Friday) grâce à une meilleure gestion de la concurrency.',
    '🛡️ Renforcement de la sécurité back-office : meilleure isolation des services sensibles et durcissement des endpoints.',
    '📈 Mise en production régulière sans interruption, améliorant la vélocité de l’équipe et la stabilité du produit.',
    '😊 Amélioration notable de la satisfaction client lors des suivis de projet (moins d’incidents récurrents).'
  ],
  technologies: [
    'Python', 'Flask', 'JavaScript', 'TypeScript', 'TailwindCSS', 'Vue.js', 'VueUse',
    'Pinia', 'TanStack Query', 'MongoDB', 'Redis', 'REST API',
    'Celery', 'Docker', 'Kubernetes', 'CI/CD', 'Git', 'Linux',
    'Storybook', 'Microservices', 'SaaS', 'Promotions Engine'
  ],
  team: 'Méthode Agile / Scrum — 5 développeurs (2 Backend, 2 Frontend, 1 DevOps)',
  link: 'https://www.onestock-retail.com/fr/'
},
  {
  id: 2,
  title: 'Développeur Python Backend – Génération automatisée de PDF dynamiques',
  description:
    'Développement d’une plateforme Django permettant la génération et la gestion automatisée de documents PDF basés sur des contenus personnalisables.',
  details: `Création d’un backend complet permettant d’éditer, prévisualiser, stocker et générer des PDFs dynamiques.
Le projet combinait un éditeur HTML enrichi, un moteur de rendu PDF optimisé et une base SQLite structurée.`,
  status: 'Terminé',
  date: 'Avril – Mai 2023',
  company: 'M2I',
  missions: [
    'Développement backend Django : modèles, vues, logique métier, endpoints.',
    'Conception de la base SQLite pour garantir fiabilité et rapidité.',
    'Intégration avancée de TinyMCE pour la création de contenus dynamiques.',
    'Mise en place d’un moteur de rendu PDF personnalisé.',
    'Optimisation du temps de génération et de la qualité du rendu final.'
  ],
  results: [
    '📝 Rendu PDF amélioré : +12% de rapidité sur le temps de génération.',
    '🔍 Réduction des erreurs de parsing grâce à une meilleure structuration des données.',
    '✨ UX améliorée pour les utilisateurs grâce à TinyMCE.',
    '🎯 Processus complet de création documentaire fluidifié.',
  ],
  technologies: ['Python', 'Django', 'SQLite', 'TinyMCE', 'HTML/CSS', 'PDF Engine'],
  team: '4 personnes (1 Backend, 2 Mobile, 1 UI/UX Designer)',
  link: '#'
},
  {
  id: 3,
  title: 'Développeur Python – Système de Clavier Syllabique PIAmot',
  description:
    'Développement de la seconde génération du clavier syllabique PIAmot en Python et C, avec un focus sur les performances, la vitesse et la robustesse.',
  details: `PIAmot est un clavier intelligent basé sur un moteur syllabique permettant une saisie plus rapide et prédictive.
Le projet impliquait l’ingénierie logicielle, l’optimisation algorithmique et l’amélioration de la sécurité.
  `,
  status: 'Terminé',
  date: 'Mars – Septembre 2022',
  company: 'PIAmot',
  missions: [
    'Pilotage technique d’une équipe multi-profils.',
    'Développement Python/C de la logique prédictive et du moteur d’assemblage syllabique.',
    'Optimisation bas niveau pour améliorer la vitesse d’exécution.',
    'Mise en place de mécanismes de sécurité et de gestion fiable des données utilisateur.'
  ],
  results: [
    '⚡ Accélération du moteur syllabique : ~10% plus rapide.',
    '🎯 Amélioration de la précision de saisie et de la fluidité globale.',
    '🛡️ Renforcement de la robustesse et réduction des crashs.',
    '🚀 Stabilité accrue lors d’un usage intensif.',
    '😊 bêta-testeurs satisfaits : retour positif sur vitesse et confort d’écriture.'
  ],
  technologies: ['Python', 'C', 'Linux', 'Git', 'Algorithmie', 'Optimisation bas niveau'],
  team: '6 personnes (Backend, Frontend, Data Scientist, PO)',
  link: 'https://piamot.com/'
}

];
</script>

<template>
  <section id="experience" class="min-h-screen flex flex-col items-center justify-center px-4">
    <h2 class="mobile-text text-4xl font-bold text-[#CFAF71] mb-4">Experiences professionnelles</h2>
    <p class="text-lg text-[#CFAF71] mb-8">veuillez cliquer sur les cartes pour plus de détails</p>

    <div class="flex flex-col items-center justify-center gap-6">
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        :title="project.title"
        :description="project.description"
        :details="project.details"
        :status="project.status"
        :date="project.date"
        :company="project.company"
        :missions="project.missions"
        :results="project.results"
        :technologies="project.technologies"
        :team="project.team"
        :link="project.link"
      />
    </div>
  </section>
</template>

<style scoped>
    @media (max-width: 590px) {
  .mobile-text {
    font-size: 24px;
  }
}
</style>