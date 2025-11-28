
<script setup lang="ts">
import { ref, onMounted } from 'vue'

const showLoader = ref(true)

onMounted(() => {
  // Masquer le loader après 2 secondes
  setTimeout(() => {
    showLoader.value = false
  }, 800)
})
</script>

<template>
      <!-- Loader overlay - affiché pendant 2 secondes au chargement -->
  <div 
    v-if="showLoader" 
    class="fixed inset-0 w-full h-full bg-white z-[9999] flex items-center justify-center animate-fadeOut"
  >
    <div class="absolute top-1/2 left-1/2 -ml-[50px] animate-speeder">
      <span class="absolute h-[5px] w-[35px] bg-black top-[-19px] left-[60px] rounded-[2px_10px_1px_0]">
        <span class="absolute w-[30px] h-[1px] bg-black animate-fazer1"></span>
        <span class="absolute w-[30px] h-[1px] bg-black top-[3px] animate-fazer2"></span>
        <span class="absolute w-[30px] h-[1px] bg-black top-[1px] animate-fazer3"></span>
        <span class="absolute w-[30px] h-[1px] bg-black top-1 animate-fazer4"></span>
      </span>
      <div class="base">
        <span class="absolute w-0 h-0 border-t-[6px] border-t-transparent border-r-[100px] border-r-black border-b-[6px] border-b-transparent"></span>
        <div class="absolute h-3 w-5 bg-black rounded-t-[20px] -rotate-[40deg] -right-[125px] -top-[15px]"></div>
      </div>
    </div>
    <div class="absolute w-full h-full">
      <span class="absolute h-0.5 w-1/5 bg-black top-[20%] animate-lf"></span>
      <span class="absolute h-0.5 w-1/5 bg-black top-[40%] animate-lf2"></span>
      <span class="absolute h-0.5 w-1/5 bg-black top-[60%] animate-lf3"></span>
      <span class="absolute h-0.5 w-1/5 bg-black top-[80%] animate-lf4"></span>
    </div>
  </div>
  
</template>
<style scoped>
/* From Uiverse.io by anand_4957 */ 
/* Animation fadeOut pour l'overlay */
@keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
    visibility: hidden;
  }
}

.animate-fadeOut {
  animation: fadeOut 0.3s ease-out 0.5s forwards;
}

/* Pseudo-éléments pour le base span */
.base span::before {
  content: "";
  height: 22px;
  width: 22px;
  border-radius: 50%;
  background: #000;
  position: absolute;
  right: -110px;
  top: -16px;
}

.base span::after {
  content: "";
  position: absolute;
  width: 0;
  height: 0;
  border-top: 0 solid transparent;
  border-right: 55px solid #000;
  border-bottom: 16px solid transparent;
  top: -16px;
  right: -98px;
}

/* Face pseudo-élément */
.base > div::after {
  content: "";
  height: 12px;
  width: 12px;
  background: #000;
  right: 4px;
  top: 7px;
  position: absolute;
  transform: rotate(40deg);
  transform-origin: 50% 50%;
  border-radius: 0 0 0 2px;
}

/* Animations pour les fazers */
@keyframes fazer1 {
  0% {
    left: 0;
  }
  100% {
    left: -80px;
    opacity: 0;
  }
}

@keyframes fazer2 {
  0% {
    left: 0;
  }
  100% {
    left: -100px;
    opacity: 0;
  }
}

@keyframes fazer3 {
  0% {
    left: 0;
  }
  100% {
    left: -50px;
    opacity: 0;
  }
}

@keyframes fazer4 {
  0% {
    left: 0;
  }
  100% {
    left: -150px;
    opacity: 0;
  }
}

@keyframes speeder {
  0% {
    transform: translate(2px, 1px) rotate(0deg);
  }
  10% {
    transform: translate(-1px, -3px) rotate(-1deg);
  }
  20% {
    transform: translate(-2px, 0px) rotate(1deg);
  }
  30% {
    transform: translate(1px, 2px) rotate(0deg);
  }
  40% {
    transform: translate(1px, -1px) rotate(1deg);
  }
  50% {
    transform: translate(-1px, 3px) rotate(-1deg);
  }
  60% {
    transform: translate(-1px, 1px) rotate(0deg);
  }
  70% {
    transform: translate(3px, 1px) rotate(-1deg);
  }
  80% {
    transform: translate(-2px, -1px) rotate(1deg);
  }
  90% {
    transform: translate(2px, 1px) rotate(0deg);
  }
  100% {
    transform: translate(1px, -2px) rotate(-1deg);
  }
}

@keyframes lf {
  0% {
    left: 200%;
  }
  100% {
    left: -200%;
    opacity: 0;
  }
}

@keyframes lf2 {
  0% {
    left: 200%;
  }
  100% {
    left: -200%;
    opacity: 0;
  }
}

@keyframes lf3 {
  0% {
    left: 200%;
  }
  100% {
    left: -100%;
    opacity: 0;
  }
}

@keyframes lf4 {
  0% {
    left: 200%;
  }
  100% {
    left: -100%;
    opacity: 0;
  }
}

/* Classes d'animation Tailwind personnalisées */
.animate-speeder {
  animation: speeder 0.4s linear infinite;
}

.animate-fazer1 {
  animation: fazer1 0.2s linear infinite;
}

.animate-fazer2 {
  animation: fazer2 0.4s linear infinite;
}

.animate-fazer3 {
  animation: fazer3 0.4s linear infinite;
  animation-delay: -1s;
}

.animate-fazer4 {
  animation: fazer4 1s linear infinite;
  animation-delay: -1s;
}

.animate-lf {
  animation: lf 0.6s linear infinite;
  animation-delay: -5s;
}

.animate-lf2 {
  animation: lf2 0.8s linear infinite;
  animation-delay: -1s;
}

.animate-lf3 {
  animation: lf3 0.6s linear infinite;
}

.animate-lf4 {
  animation: lf4 0.5s linear infinite;
  animation-delay: -3s;
}

</style>