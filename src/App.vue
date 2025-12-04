<script setup lang="ts">
import Home from './pages/Home.vue'
</script>

<template>
  <Home />
</template>

<style>
/* IMPORTANT: Pas de "scoped" pour que ça s'applique partout */

/* Style global pour la scrollbar sur toute l'application */
* {
  scrollbar-width: thin;
  scrollbar-color: #CFAF71 transparent;
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

*::-webkit-scrollbar-thumb:hover {
  background: #b8955a;
}

/* Scrollbar pour le body/html (page principale) */
html {
  scrollbar-width: thin;
  scrollbar-color: #000000 rgba(207, 175, 113, 0.1);
  scroll-behavior: smooth;
}

html::-webkit-scrollbar {
  width: 8px;
}

html::-webkit-scrollbar-track {
  background: rgba(207, 175, 113, 0.05);
}

html::-webkit-scrollbar-thumb {
  background: #CFAF71;
  border-radius: 4px;
}

html::-webkit-scrollbar-thumb:hover {
  background: #b8955a;
}
</style>