<script setup lang="ts">
import ProjectCard from './ProjectCard.vue';

const projects = [
  {
    id: 1,
    title: 'Plateforme E-commerce Multi-vendeurs',
    description: 'Développement complet d\'une plateforme e-commerce moderne avec gestion multi-vendeurs, panier intelligent, système de paiement sécurisé et tableau de bord administrateur avancé.',
    status: 'Terminé',
    date: 'Janvier 2024 - Juin 2024',
    company: 'TechCommerce Solutions',
    missions: [
      'Conception et développement de l\'architecture backend avec Django REST Framework',
      'Création d\'interfaces utilisateur réactives avec Vue.js et Tailwind CSS',
      'Intégration de passerelles de paiement (Stripe, PayPal) avec gestion sécurisée des transactions',
      'Mise en place d\'un système de gestion des stocks en temps réel',
      'Développement d\'API RESTful documentées avec Swagger',
      'Optimisation des performances et mise en cache avec Redis'
    ],
    results: [
      'Réduction de 40% du temps de chargement des pages',
      'Augmentation de 60% du taux de conversion',
      'Gestion de plus de 500 transactions par jour',
      'Support de 50+ vendeurs actifs sur la plateforme',
      'Satisfaction client de 92%'
    ],
    technologies: ['Python', 'Django', 'Vue.js', 'PostgreSQL', 'Redis', 'Docker', 'Stripe API', 'AWS S3', 'Celery'],
    team: 'Équipe de 5 développeurs (2 Backend, 2 Frontend, 1 DevOps)',
    link: '#'
  },
  {
    id: 2,
    title: 'Application Mobile de Suivi Fitness',
    description: 'Application mobile cross-platform permettant le suivi des performances sportives, la définition d\'objectifs personnalisés et la synchronisation avec des dispositifs connectés.',
    status: 'En cours',
    date: 'Juillet 2024 - Présent',
    company: 'FitTech Innovation',
    missions: [
      'Développement backend avec FastAPI pour des performances optimales',
      'Création d\'algorithmes de calcul de performances et recommandations personnalisées',
      'Intégration avec des APIs de dispositifs connectés (Fitbit, Garmin)',
      'Mise en place d\'un système de notifications push intelligent',
      'Développement de graphiques et visualisations de données interactifs',
      'Implémentation d\'un système de gamification pour la motivation'
    ],
    results: [
      '10 000+ téléchargements en phase beta',
      'Note moyenne de 4.7/5 sur les stores',
      'Temps de réponse API < 100ms',
      'Synchronisation en temps réel avec 15+ appareils connectés',
      'Engagement utilisateur de 85% après 30 jours'
    ],
    technologies: ['Python', 'FastAPI', 'React Native', 'MongoDB', 'Docker', 'Firebase', 'GraphQL', 'JWT', 'WebSocket'],
    team: 'Équipe de 4 développeurs (1 Backend, 2 Mobile, 1 Designer UX/UI)',
    link: '#'
  },
  {
    id: 3,
    title: 'Dashboard Analytics B2B',
    description: 'Plateforme d\'analyse de données en temps réel pour entreprises avec visualisations avancées, rapports automatisés et prédictions basées sur le machine learning.',
    status: 'Terminé',
    date: 'Mars 2023 - Décembre 2023',
    company: 'DataViz Pro',
    missions: [
      'Architecture et développement d\'une plateforme d\'analytics scalable',
      'Création de dashboards interactifs avec visualisations personnalisables',
      'Implémentation de pipelines de traitement de données avec Airflow',
      'Développement de modèles ML pour prédictions et détection d\'anomalies',
      'Mise en place d\'un système de génération de rapports PDF automatisés',
      'Optimisation des requêtes SQL complexes pour performances maximales'
    ],
    results: [
      'Traitement de 2 millions+ de données par jour',
      'Génération de rapports 10x plus rapide',
      'Réduction de 70% du temps d\'analyse pour les clients',
      'Précision des prédictions ML de 87%',
      'Adoption par 30+ entreprises clientes',
      'ROI client moyen de +150% en 6 mois'
    ],
    technologies: ['Python', 'Flask', 'React', 'PostgreSQL', 'Pandas', 'Scikit-learn', 'D3.js', 'Docker', 'Kubernetes', 'Apache Airflow'],
    team: 'Équipe de 6 personnes (2 Backend, 2 Frontend, 1 Data Scientist, 1 Product Owner)',
    link: '#'
  }
];
</script>

<template>
  <section id="experience" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">
    <h2 class="text-4xl font-bold text-[#CFAF71] mb-12">Experiences professionnelles</h2>

    <div class="flex flex-wrap justify-center gap-6 w-full max-w-7xl">
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        :title="project.title"
        :description="project.description"
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