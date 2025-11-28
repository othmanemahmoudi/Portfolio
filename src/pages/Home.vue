<script setup lang="ts">
import Header from '../layouts/Header.vue'
import DefaultLayout from '../layouts/DefaultLayout.vue'
import Footer from '../layouts/Footer.vue'
import SuperOthmaneLoader from '../components/SuperOthmaneLoader.vue'
</script>

<template>
  <div class="min-h-screen flex flex-col">
    <SuperOthmaneLoader />
    <Header />
    <main class="flex-1 pt-20">
      <DefaultLayout />
    </main>
    <Footer />
  </div>
</template>

<style scoped>

</style>

