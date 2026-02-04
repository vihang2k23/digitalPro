<template>
  <header class="fixed top-0 w-full bg-white/95 backdrop-blur-sm shadow-sm z-50 transition-all duration-300" :class="{ 'py-2': scrolled, 'py-4': !scrolled }">
    <nav class="container mx-auto px-4">
      <div class="flex items-center justify-between">
        <!-- Logo -->
        <router-link to="/" class="flex items-center space-x-2 cursor-pointer" @click="closeMobileMenu">
          <div class="w-10 h-10 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-lg flex items-center justify-center">
            <span class="text-white font-bold text-xl">DM</span>
          </div>
          <span class="text-xl font-bold gradient-text">DigitalPro</span>
        </router-link>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <router-link 
            v-for="item in navigation" 
            :key="item.name"
            :to="item.path"
            class="text-gray-700 hover:text-primary-600 font-medium transition-colors duration-200 relative group"
          >
            {{ item.name }}
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 transition-all duration-300 group-hover:w-full"></span>
          </router-link>
          <button class="btn-primary" @click="goToContact">
            Get Started
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <button 
          @click="toggleMobileMenu"
          class="md:hidden p-2 rounded-lg hover:bg-gray-100 transition-colors duration-200"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" :d="mobileMenuOpen ? 'M6 18L18 6M6 6l12 12' : 'M4 6h16M4 12h16M4 18h16'"></path>
          </svg>
        </button>
      </div>

      <!-- Mobile Navigation -->
      <div v-show="mobileMenuOpen" class="md:hidden mt-4 pb-4 border-t border-gray-200 pt-4">
        <div class="flex flex-col space-y-3">
          <router-link 
            v-for="item in navigation" 
            :key="item.name"
            :to="item.path"
            @click="closeMobileMenu"
            class="text-gray-700 hover:text-primary-600 font-medium transition-colors duration-200 py-2"
          >
            {{ item.name }}
          </router-link>
          <button class="btn-primary w-full" @click="goToContact">
            Get Started
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import { useRouter } from 'vue-router'

const scrolled = ref(false)
const mobileMenuOpen = ref(false)
const router = useRouter()

const navigation = [
  { name: 'Home', path: '/' },
  { name: 'Services', path: '/services' },
  { name: 'About', path: '/about' },
  { name: 'Contact', path: '/contact' },
]

const handleScroll = () => {
  scrolled.value = window.scrollY > 20
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

const goToContact = () => {
  router.push('/contact')
  closeMobileMenu()
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
