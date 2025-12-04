<template>
  <div
    class="fixed inset-0 bg-black/60 flex items-center justify-center z-50 p-4"
    @click.self="$emit('close')"
  >
    <div class="bg-white rounded-2xl shadow-2xl w-[90%] h-[75%] flex flex-col relative animate-fadeInModal border border-[#CFAF71]/30 overflow-hidden">
      
      <!-- Header fixe -->
      <div class="flex-shrink-0 p-6 pb-4 border-b border-[#CFAF71]/20 bg-black backdrop-blur-sm">
        <button
          class="absolute top-4 right-4 text-[#CFAF71] transition-colors duration-200 w-8 h-8 flex items-center justify-center rounded-full hover:bg-[#CFAF71]/10 cursor-pointer"
          @click="$emit('close')"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
        
        <div class="flex items-center">
          <h2 class="text-3xl font-bold text-[#CFAF71]">{{ title }}</h2>
            <div class="flex px-5 gap-3 text-sm">
                <span class="px-3 py-1 bg-[#CFAF71]/10 text-[#CFAF71] rounded-full font-medium">
                 {{ status }}
                </span>
                <span class="px-3 py-1 bg-[#CFAF71]/10 text-[#CFAF71] rounded-full">
                 {{ date }}
             </span>
          </div>
        </div>
        
      </div>

      <!-- Contenu scrollable -->
      <div class="flex-1 overflow-y-auto px-6 py-6 custom-scrollbar">
        <p class="text-[#2A2A2A]/80 text-lg leading-relaxed mb-6">
          {{ description }}
        </p>
        
        <!-- Contenu de test pour voir le scroll -->
        <div class="space-y-4">
          <p class="text-[#2A2A2A]/70">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          </p>
          <p class="text-[#2A2A2A]/70">
            Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </p>
          <p class="text-[#2A2A2A]/70">
            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
          </p>
          <p class="text-[#2A2A2A]/70">
            Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </p>
          <p class="text-[#2A2A2A]/70">
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.
          </p>
          <p class="text-[#2A2A2A]/70">
            Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores.
          </p>
          <p class="text-[#2A2A2A]/70">
            Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores.
          </p>
        </div>
      </div>

      <!-- Footer avec bouton à droite -->
      <div class="flex-shrink-0 p-6 pt-4 bg-white/95 backdrop-blur-sm flex justify-end">
        <button
          @click="$emit('close')"
          class="bg-black cursor-pointer text-[#CFAF71] font-semibold py-3 px-8 rounded-lg transition-colors duration-200"
        >
          Fermer
        </button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps({
  title: String,
  description: String,
  image: String,
  status: String,
  date: String
})
</script>

<style scoped>
@keyframes fadeInModal {
  from {
    opacity: 0;
    transform: scale(0.95) translateY(-20px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

.animate-fadeInModal {
  animation: fadeInModal 0.3s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}

/* Scrollbar personnalisée */
.custom-scrollbar {
  scrollbar-width: thin;
  scrollbar-color: #CFAF71 transparent;
}

.custom-scrollbar::-webkit-scrollbar {
  width: 6px;
}

.custom-scrollbar::-webkit-scrollbar-track {
  background: transparent;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
  background: #CFAF71;
  border-radius: 3px;
  transition: background 0.2s;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
  background: #b8955a;
}
</style>