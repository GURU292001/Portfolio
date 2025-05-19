<template>
  <header :class="[
    'fixed top-0 left-0 m-0 p-0 right-0 z-40  ',
    isScrolled
      ? 'bg-gradient-to-r from-gray-900 via-gray-700 to-black/80 backdrop-blur-md text-white p-4 rounded-lg py-3'
      : 'bg-gradient-to-r from-gray-900 via-gray-700 to-black/80 backdrop-blur-md text-white p-4  py-4'
  ]">
    <div class="container mx-auto px-4 flex justify-center items-center">
      <!-- <a href="#" class="text-xl md:text-2xl font-bold text-white">Portfolio</a> -->

      <!-- Desktop Navigation -->
      <nav class="hidden md:block">
        <ul class="flex space-x-6">
          <li v-for="item in menuItems" :key="item.name">
            <a :href="item.href" class="nav-link !font-bold !text-blue-100">
              {{ item.name }}
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Mobile Floating Navigation Bar -->
  <nav v-if="isMobile" class="fixed bottom-6 left-0 right-0 z-50 flex justify-center">
    <div
      class="flex space-x-8 px-8 py-3 bg-gradient-to-r from-gray-900 via-gray-800 to-black/90 backdrop-blur-md shadow-lg rounded-full border border-white/10">
      <a v-for="item in menuItems" :key="item.name" :href="item.href"
        class="flex flex-col items-center text-white hover:text-green-400 transition-all duration-300">
        <v-icon class="text-xl mb-1">{{ item.icon }}</v-icon>
        <span class="text-xs font-medium tracking-wide">{{ item.name }}</span>
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
.nav-link {
  @apply relative text-blue-500;
}

.nav-link::before {
  content: '';
  @apply absolute left-0 -bottom-1 w-0 h-0.5 bg-gradient-to-r from-white via-gray-400 to-white transition-all duration-300;
}

.nav-link:hover::before {
  @apply w-full;
}

.nav-link:hover {
  background: linear-gradient(90deg, #ffffff 0%, #aaaaaa 50%, #ffffff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  transition: all 0.5s ease-in-out;
}
</style>
