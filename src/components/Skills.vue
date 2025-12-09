<script setup lang="ts">
import SkillCard from './SkillCard.vue'
import SkillsSphere from '../components/SkillsSphere.vue'

// 👉 Import des SVG depuis assets/icons
import vueIcon from '../assets/icons/vue.svg'   
import djangoIcon from '../assets/icons/Django.svg'
import flaskIcon from '../assets/icons/Flask.svg'
import tailwindIcon from '../assets/icons/Tailwind CSS.svg'
import dockerIcon from '../assets/icons/Docker.svg'
import kubernetesIcon from '../assets/icons/Kubernetes.svg'
import gitIcon from '../assets/icons/Git.svg'
import graphqlIcon from '../assets/icons/GraphQL.svg'
import pythonIcon from '../assets/icons/Python.svg'
import javascriptIcon from '../assets/icons/JavaScript.svg'
import typescriptIcon from '../assets/icons/TypeScript.svg'
import sqlIcon from '../assets/icons/SQL.svg'
import cIcon from '../assets/icons/C.svg'
import microservicesIcon from '../assets/icons/Microservices.svg'
import fastApi from '../assets/icons/FastAPI.svg'
import mongodbIcon from '../assets/icons/MongoDB.svg'
import redisIcon from '../assets/icons/Redis.svg'
import sqliteIcon from '../assets/icons/SQLite.svg'
import npmIcon from '../assets/icons/Npm.svg'
import storyBookIcon from '../assets/icons/Storybook.svg'
import agileIcon  from '../assets/icons/Agile.svg'
import piniaIcon from '../assets/icons/Pinia.svg'
import devopsIcon from '../assets/icons/Devops.svg'
import vueuseIcon from '../assets/icons/Vueuse.svg'
import figmaIcon from '../assets/icons/Figma.svg'
import jiraIcon from '../assets/icons/Jira.svg'
import vscodeIcon from '../assets/icons/VsCode.svg'
import pycharmIcon from '../assets/icons/PyCharm.svg'
import cssIcon from '../assets/icons/CSS3.svg'
import htmlIcon from '../assets/icons/HTML5.svg'
import kafkaIcon from '../assets/icons/Kafka.svg'
import nginxIcon from '../assets/icons/Nginx.svg'
import javaIcon from '../assets/icons/Java.svg'
import pytestIcon from '../assets/icons/Pytest.svg'
import saasIcon from '../assets/icons/Saas.svg'
// Tu continues à importer les autres SVG dont tu as besoin…

const skillCategories = [
  {
    title: 'Programmation',
    skills: [
      { id: 1, name: 'Python', icon: pythonIcon, category: 'Langage', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1526379095098-d400fd0bf935?w=800' },
      { id: 7, name: 'Java', icon: javaIcon, category: 'Langage', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1579468118864-1b9ea3c0db4a?w=800' },
      { id: 2, name: 'JavaScript', icon: javascriptIcon, category: 'Langage', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1579468118864-1b9ea3c0db4a?w=800' },
      { id: 5, name: 'C', icon: cIcon, category: 'Langage', percentage: 75, bgImage: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800' },{ id: 4, name: 'SQL', icon: sqlIcon, category: 'Langage', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=800' },      { id: 6, name: 'GraphQL', icon: graphqlIcon, category: 'Langage', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=800' },
      { id: 8, name: 'HTML', icon: htmlIcon, category: 'Langage', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1579468118864-1b9ea3c0db4a?w=800' },
      { id: 9, name: 'CSS', icon: cssIcon, category: 'Langage', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1587620962725-abab7fe55159?w=800' },
      { id: 3, name: 'TypeScript', icon: typescriptIcon, category: 'Langage', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1587620962725-abab7fe55159?w=800' },
    ]
  },
  {
    title: 'Méthodes / Architectures',
    skills: [
      { id: 7, name: 'Microservices', icon: microservicesIcon, category: 'Architecture', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=800' },
      { id: 8, name: 'REST/FAST API', icon: fastApi, category: 'Architecture', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800' },
      { id: 9, name: 'Agile/Scrum', icon: agileIcon, category: 'Méthode', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1531403009284-440f080d1e12?w=800' },
      { id: 10, name: 'TDD', icon: pytestIcon, category: 'Méthode', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1516116216624-53e697fedbea?w=800' },
      { id: 11, name: 'CI/CD', icon: devopsIcon, category: 'Méthode', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1618401471353-b98afee0b2eb?w=800' },
      { id: 12, name: 'SaaS', icon: saasIcon, category: 'Architecture', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=800' }
    ]
  },
  {
    title: 'Framework / API / CMS',
    skills: [
      { id: 13, name: 'Django', icon: djangoIcon, category: 'Backend', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=800' },
      { id: 14, name: 'Flask', icon: flaskIcon, category: 'Backend', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800' },
      { id: 15, name: 'Vue.js', icon: vueIcon, category: 'Frontend', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?w=800' },
      { id: 21, name: 'VueUse', icon: vueuseIcon, category: 'Frontend', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?w=800' },

      // { id: 16, name: 'React', icon: vueIcon, category: 'Frontend', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1633356122102-3fe601e05bd2?w=800' },
      // { id: 17, name: 'Angular', icon: vueIcon, category: 'Frontend', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1555099962-4199c345e5dd?w=800' },
      { id: 18, name: 'Tailwind', icon: tailwindIcon, category: 'Frontend', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?w=800' },
      { id: 19, name: 'Pinia', icon: piniaIcon, category: 'Frontend', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?w=800' },
      { id: 20, name: 'Storybook', icon: storyBookIcon, category: 'Frontend', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1512314889357-e157c22f938d?w=800' },
    ]
  },
  {
    title: 'Stockage / Bases de Données',
    skills: [
      { id: 22, name: 'MongoDB', icon: mongodbIcon, category: 'NoSQL', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1576595580361-90a855b84b20?w=800' },
      { id: 23, name: 'Redis', icon: redisIcon, category: 'Cache', percentage: 90, bgImage: 'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800' },
      { id: 26, name: 'SQLite', icon: sqliteIcon, category: 'SQL', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=800' },
      { id: 27, name: 'Redis Streams', icon: vueIcon, category: 'Streaming', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800' }
    ]
  },
  {
    title: 'DevOps / Cloud / Streaming',
    skills: [
      { id: 28, name: 'Docker', icon: dockerIcon, category: 'DevOps', percentage: 95, bgImage: 'https://images.unsplash.com/photo-1605745341112-85968b19335b?w=800' },
      { id: 29, name: 'Kubernetes', icon: kubernetesIcon, category: 'DevOps', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1605745341112-85968b19335b?w=800' },
      { id: 36, name: 'Nginx', icon: nginxIcon, category: 'DevOps', percentage: 85, bgImage: 'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?w=800' },
      { id: 37, name: 'Apache Kafka', icon: kafkaIcon, category: 'Streaming', percentage: 80, bgImage: 'https://images.unsplash.com/photo-1519389950473-47ba0277781c?w=800' }
    ]
  },
{
  title: 'Outils / Logiciels',
  skills: [
    { id: 30, name: 'Git', icon: gitIcon, category: 'Outils', percentage: 95, bgImage: '...' },
    { id: 31, name: 'npm', icon: npmIcon, category: 'Outils', percentage: 85, bgImage: '...' },
    { id: 32, name: 'Figma', icon: figmaIcon, category: 'Logiciels', percentage: 85, bgImage: '...' },
    { id: 33, name: 'Jira Atlassian', icon: jiraIcon, category: 'Outils', percentage: 85, bgImage: '...' },
    { id: 34, name: 'Pycharm', icon: pycharmIcon, category: 'Logiciels', percentage: 85, bgImage: '...' },
    { id: 35, name: 'VScode', icon: vscodeIcon, category: 'Logiciels', percentage: 85, bgImage: '...' }

  ]
}
]

// Fonction pour regrouper les catégories par 2
const groupedCategories = []
for (let i = 0; i < skillCategories.length; i += 2) {
  groupedCategories.push(skillCategories.slice(i, i + 2))
}
</script>

<template>
  <section id="skills" class="min-h-screen flex flex-col items-center justify-center py-20 px-4">

    <div class="text-center">
      <h2 class="text-4xl font-bold text-[#CFAF71]">Compétences</h2>
    </div>

    <div class="w-full max-w-7xl space-y-16">
      <!-- On regroupe les catégories par 2 -->
      <div 
        v-for="(pair, index) in groupedCategories" 
        :key="index"
        class="flex flex-col md:flex-row gap-12 justify-center"
      >
        <div 
          v-for="category in pair" 
          :key="category.title"
          class="w-full md:w-1/2"
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
    </div>

  </section>
</template>
