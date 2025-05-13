<template>
  <header :class="[
      'fixed top-0 left-0 right-0 z-40 transition-all duration-300',
      isScrolled
          ? 'bg-black/80 shadow-md backdrop-blur-md py-3'
          : 'bg-black py-5'
  ]">
      <div class="container mx-auto px-4 flex justify-between items-center">
          <a href="#" class="text-xl md:text-2xl font-bold text-white">Portfolio</a>

          <!-- Desktop Navigation -->
          <nav class="hidden md:block">
              <ul class="flex space-x-8">
                  <li v-for="item in menuItems" :key="item.name">
                      <a :href="item.href" class="text-white hover:text-green-500 transition-colors duration-300">
                          {{ item.name }}
                      </a>
                  </li>
              </ul>
          </nav>
      </div>
  </header>

  <!-- Mobile Floating Navigation Bar -->
  <nav v-if="isMobile" class="fixed bottom-8 left-0 right-0 z-50 flex justify-center">
      <div class="flex space-x-4 py-3 px-6 bg-black/90 backdrop-blur-md shadow-lg rounded-full">
          <a v-for="item in menuItems" :key="item.name" :href="item.href"
              class="flex flex-col items-center space-y-1 text-white hover:text-green-500 transition-colors duration-300 px-3">
              <!-- Use Vuetify icons or custom SVGs -->
              <v-icon>mdi-home</v-icon> <!-- Use the actual icon here -->
              <span class="text-xs">{{ item.name }}</span>
          </a>
      </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobile = ref(false)

const handleScroll = () => {
    isScrolled.value = window.scrollY > 50
}

const handleResize = () => {
    isMobile.value = window.innerWidth < 768
}

onMounted(() => {
    handleResize()
    window.addEventListener('scroll', handleScroll)
    window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
    window.removeEventListener('resize', handleResize)
})

const menuItems = [
    { name: 'Home', href: '#home' },
    { name: 'About', href: '#about' },
    { name: 'Projects', href: '#projects' },
    { name: 'Contact', href: '#contact' }
]
</script>

<style scoped>
/* Optional: Further customize text colors, background colors, or transitions */
</style>
