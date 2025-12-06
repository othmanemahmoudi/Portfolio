<script setup lang="ts">
import SkillCard from './SkillCard.vue'
import SkillsSphere from '../components/SkillsSphere.vue'

const skillCategories = [
  {
    title: 'Programmation',
    skills: [
      { id: 1, name: 'Python', icon: '🐍', category: 'Langage', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1526379095098-d400fd0bf935?w=800' },
      { id: 2, name: 'JavaScript', icon: '⚡', category: 'Langage', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1579468118864-1b9ea3c0db4a?w=800' },
      { id: 3, name: 'TypeScript', icon: '📘', category: 'Langage', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1587620962725-abab7fe55159?w=800' },
      { id: 4, name: 'SQL', icon: '🗄️', category: 'Langage', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=800' },
      { id: 5, name: 'C', icon: '⚙️', category: 'Langage', percentage: 75, bgImage: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800' },
      { id: 6, name: 'GraphQL', icon: '🔷', category: 'Langage', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=800' }
    ]
  },
  {
    title: 'Méthodes / Architectures',
    skills: [
      { id: 7, name: 'Microservices', icon: '🧩', category: 'Architecture', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=800' },
      { id: 8, name: 'REST API', icon: '🔌', category: 'Architecture', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800' },
      { id: 9, name: 'Agile/Scrum', icon: '🔄', category: 'Méthode', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1531403009284-440f080d1e12?w=800' },
      { id: 10, name: 'TDD', icon: '✅', category: 'Méthode', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=800' },
      { id: 11, name: 'CI/CD', icon: '🔁', category: 'Méthode', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800' },
      { id: 12, name: 'SaaS', icon: '☁️', category: 'Architecture', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=800' }
    ]
  },
  {
    title: 'Framework / API / CMS',
    skills: [
      { id: 13, name: 'Django', icon: '🎯', category: 'Backend', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=800' },
      { id: 14, name: 'Flask', icon: '🧪', category: 'Backend', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800' },
      { id: 15, name: 'Vue.js', icon: '💚', category: 'Frontend', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?w=800' },
      { id: 16, name: 'React', icon: '⚛️', category: 'Frontend', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1633356122102-3fe601e05bd2?w=800' },
      { id: 17, name: 'Angular', icon: '🅰️', category: 'Frontend', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1555099962-4199c345e5dd?w=800' },
      { id: 18, name: 'Tailwind CSS', icon: '🎨', category: 'Frontend', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?w=800' },
      { id: 19, name: 'Pinia', icon: '🍍', category: 'Frontend', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?w=800' },
      { id: 20, name: 'Storybook', icon: '📚', category: 'Frontend', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1512314889357-e157c22f938d?w=800' },
      { id: 21, name: 'VueUse', icon: '🔧', category: 'Frontend', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?w=800' }
    ]
  },
  {
    title: 'Stockage / Bases de Données',
    skills: [
      { id: 22, name: 'MongoDB', icon: '🍃', category: 'NoSQL', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1576595580361-90a855b84b20?w=800' },
      { id: 23, name: 'Redis', icon: '🔴', category: 'Cache', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800' },
      { id: 24, name: 'PostgreSQL', icon: '🐘', category: 'SQL', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=800' },
      { id: 25, name: 'MySQL', icon: '🐬', category: 'SQL', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1593642532400-2682810df593?w=800' },
      { id: 26, name: 'SQLite', icon: '💾', category: 'SQL', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=800' },
      { id: 27, name: 'Redis Streams', icon: '📡', category: 'Streaming', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800' }
    ]
  },
  {
    title: 'DevOps / Cloud / IA',
    skills: [
      { id: 28, name: 'Docker', icon: '🐳', category: 'DevOps', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1605745341112-85968b19335b?w=800' },
      { id: 29, name: 'Kubernetes', icon: '☸️', category: 'DevOps', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1605745341112-85968b19335b?w=800' },
      { id: 30, name: 'AWS', icon: '☁️', category: 'Cloud', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=800' },
      { id: 31, name: 'Jenkins', icon: '👷', category: 'CI/CD', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800' },
      { id: 32, name: 'GitHub Actions', icon: '🚀', category: 'CI/CD', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800' },
      { id: 33, name: 'Machine Learning', icon: '🤖', category: 'IA', percentage: 75, bgImage: 'https://images.unsplash.com/photo-1555255707-c07966088b7b?w=800' },
      { id: 34, name: 'Deep Learning', icon: '🧠', category: 'IA', percentage: 70, bgImage: 'https://images.unsplash.com/photo-1677442136019-21780ecad995?w=800' },
      { id: 35, name: 'RabbitMQ', icon: '🐰', category: 'Messaging', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800' }
    ]
  },
  {
    title: 'Outils / Logiciels',
    skills: [
      { id: 36, name: 'Git', icon: '📦', category: 'Outil', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800' },
      { id: 37, name: 'npm', icon: '📦', category: 'Outil', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1619410283995-43d9134e7656?w=800' },
      { id: 38, name: 'TinyMCE', icon: '✍️', category: 'Éditeur', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1455390582262-044cdead277a?w=800' },
      { id: 39, name: 'Testing', icon: '🧪', category: 'QA', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=800' },
      { id: 40, name: 'UX/UI Design', icon: '🎨', category: 'Design', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1561070791-2526d30994b5?w=800' }
    ]
  }
]
</script>

<template>
  <section id="skills" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">

    <div class="text-center">
      <h2 class="text-4xl font-bold text-[#CFAF71]">Compétences</h2>
    </div>

    <div class="w-full max-w-7xl space-y-16">
      <!-- <SkillsSphere /> -->
      <div 
        v-for="category in skillCategories" 
        :key="category.title"
        class="w-full"
      >
        <!-- Titre de catégorie -->
        <h3 class="text-1xl font-semibold mb-6 text-[#CFAF71] text-center">
          {{ category.title }}
        </h3>

        <div class="flex flex-wrap justify-center gap-4">
          <SkillCard
            v-for="skill in category.skills"
            :key="skill.id"
            :name="skill.name"
            :icon="skill.icon"
            :category="skill.category"
            :bgImage="skill.bgImage"
          />
        </div>
      </div>
    </div>

  </section>
</template>
