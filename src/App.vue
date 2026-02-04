<template>
  <div id="app" class="min-h-screen">
    <AppHeader />
    <main class="pt-16">
      <RouterView v-slot="{ Component }">
        <Transition name="page" mode="out-in">
          <component :is="Component" />
        </Transition>
      </RouterView>
    </main>
    <AppFooter />
  </div>

  <Teleport to="body">
    <a
      :href="whatsappHref"
      target="_blank"
      rel="noopener noreferrer"
      class="fixed bottom-6 right-6 z-[9999] inline-flex items-center justify-center w-14 h-14 rounded-full shadow-lg bg-[#25D366] text-white hover:shadow-xl transition-all duration-300"
      aria-label="Chat on WhatsApp"
      title="Chat on WhatsApp"
    >
      <WhatsAppIcon class="w-7 h-7 pointer-events-none" />
    </a>
  </Teleport>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { RouterView } from 'vue-router'
import AppHeader from '@/components/ui/AppHeader.vue'
import AppFooter from '@/components/ui/AppFooter.vue'
import WhatsAppIcon from '@/components/icons/WhatsAppIcon.vue'

const whatsappPhone = '+15551234567'
const whatsappMessage = 'Hi! I\'m interested in your digital marketing services.'

const whatsappHref = computed(() => {
  const phone = whatsappPhone.replace(/[^\d]/g, '')
  return `https://wa.me/${phone}?text=${encodeURIComponent(whatsappMessage)}`
})
</script>

<style>
/* Page transition animations */
.page-enter-active,
.page-leave-active {
  transition: all 0.4s ease;
}

.page-enter-from {
  opacity: 0;
  transform: translateY(30px);
}

.page-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}

/* Smooth scrolling */
html {
  scroll-behavior: smooth;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(135deg, #3b82f6, #14b8a6);
  border-radius: 5px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(135deg, #2563eb, #0d9488);
}
</style>
