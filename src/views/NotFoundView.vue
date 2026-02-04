<template>
  <div class="min-h-screen bg-gradient-to-br from-primary-50 via-white to-secondary-50 flex items-center justify-center">
    <div class="text-center max-w-2xl mx-auto px-4">
      <div class="mb-8">
        <h1 class="text-9xl font-bold gradient-text mb-4">404</h1>
        <h2 class="text-4xl font-bold text-gray-900 mb-4">Page Not Found</h2>
        <p class="text-xl text-gray-600 mb-8">
          Oops! The page you're looking for seems to have vanished into the digital void.
        </p>
      </div>
      
      <div class="space-y-4">
        <BaseButton variant="primary" size="lg" @click="$router.push('/')">
          Go Back Home
        </BaseButton>
        
        <div class="text-gray-600">
          <p>Or try one of these pages:</p>
          <div class="flex justify-center space-x-6 mt-4">
            <router-link to="/services" class="text-primary-600 hover:text-primary-700 font-medium">
              Services
            </router-link>
            <router-link to="/about" class="text-primary-600 hover:text-primary-700 font-medium">
              About Us
            </router-link>
            <router-link to="/contact" class="text-primary-600 hover:text-primary-700 font-medium">
              Contact
            </router-link>
          </div>
        </div>
      </div>
      
      <!-- Animated illustration -->
      <div class="mt-12">
        <svg class="w-64 h-64 mx-auto animate-float" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="100" cy="100" r="80" stroke="url(#gradient)" stroke-width="2" stroke-dasharray="5,5" opacity="0.3"/>
          <path d="M100 60C85 60 75 70 75 85C75 100 85 110 100 110C115 110 125 100 125 85C125 70 115 60 100 60Z" fill="url(#gradient)" opacity="0.1"/>
          <circle cx="100" cy="85" r="15" fill="url(#gradient)"/>
          <path d="M100 110V130M85 145H115" stroke="url(#gradient)" stroke-width="3" stroke-linecap="round"/>
          <defs>
            <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="100%">
              <stop offset="0%" style="stop-color:#3b82f6;stop-opacity:1" />
              <stop offset="100%" style="stop-color:#14b8a6;stop-opacity:1" />
            </linearGradient>
          </defs>
        </svg>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import BaseButton from '@/components/ui/BaseButton.vue'

onMounted(() => {
  gsap.fromTo('h1', 
    { scale: 0.5, opacity: 0 },
    { scale: 1, opacity: 1, duration: 1, ease: "elastic.out(1, 0.5)" }
  )
  
  gsap.fromTo('h2', 
    { y: 30, opacity: 0 },
    { y: 0, opacity: 1, duration: 0.8, delay: 0.3, ease: "power2.out" }
  )
  
  gsap.fromTo('p', 
    { y: 30, opacity: 0 },
    { y: 0, opacity: 1, duration: 0.8, delay: 0.5, ease: "power2.out" }
  )
  
  gsap.fromTo('.space-y-4', 
    { y: 30, opacity: 0 },
    { y: 0, opacity: 1, duration: 0.8, delay: 0.7, ease: "power2.out" }
  )
})
</script>
