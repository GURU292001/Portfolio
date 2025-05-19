<template>
    <div>
      <Header />
      <main class="mt-10">
        <slot />
        <!-- <NuxtPages/> -->
      </main>
      <Footer />
    </div>
  </template>
  
  <script setup>
  import Header from '../layouts/header.vue'
  import Footer from '../layouts/footer.vue'
  </script>
  