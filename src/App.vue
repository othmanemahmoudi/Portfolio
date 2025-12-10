<script setup lang="ts">
import Home from './pages/Home.vue'
</script>

<template>
  <Home />
</template>

<style>
/* IMPORTANT: Pas de "scoped" pour que ça s'applique partout */

/* Dark mode support */
html {
  @apply transition-colors duration-300;
}

html.dark {
  color-scheme: dark;
}

/* Style global pour la scrollbar sur toute l'application */
* {
  scrollbar-width: thin;
  scrollbar-color: #CFAF71 transparent;
}

html.dark * {
  scrollbar-color: #8B6937 transparent;
}

*::-webkit-scrollbar {
  width: 6px;
  height: 6px;
}

*::-webkit-scrollbar-track {
  background: transparent;
}

*::-webkit-scrollbar-thumb {
  background: #CFAF71;
  border-radius: 3px;
  transition: background 0.2s;
}

html.dark *::-webkit-scrollbar-thumb {
  background: #8B6937;
}

*::-webkit-scrollbar-thumb:hover {
  background: #b8955a;
}

html.dark *::-webkit-scrollbar-thumb:hover {
  background: #CFAF71;
}

/* Scrollbar pour le body/html (page principale) */
html {
  scrollbar-width: thin;
  scrollbar-color: #000000 rgba(207, 175, 113, 0.1);
  scroll-behavior: smooth;
}

html.dark {
  scrollbar-color: #8B6937 rgba(207, 175, 113, 0.1);
}

html::-webkit-scrollbar {
  width: 8px;
}

html::-webkit-scrollbar-track {
  background: rgba(207, 175, 113, 0.05);
}

html.dark::-webkit-scrollbar-track {
  background: rgba(207, 175, 113, 0.02);
}

html::-webkit-scrollbar-thumb {
  background: #CFAF71;
  border-radius: 4px;
}

html.dark::-webkit-scrollbar-thumb {
  background: #8B6937;
}

html::-webkit-scrollbar-thumb:hover {
  background: #b8955a;
}

html.dark::-webkit-scrollbar-thumb:hover {
  background: #CFAF71;
}
</style>