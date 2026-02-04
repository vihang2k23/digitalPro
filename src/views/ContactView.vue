<template>
  <div class="min-h-screen">
    <!-- Hero Section -->
    <section class="py-20 bg-gradient-to-br from-primary-50 via-white to-secondary-50">
      <div class="container mx-auto px-4">
        <div class="text-center max-w-4xl mx-auto">
          <h1 class="text-4xl md:text-6xl font-bold mb-6">
            <span class="gradient-text">Contact Us</span>
          </h1>
          <p class="text-xl text-gray-600">
            Ready to grow your business? Let's discuss how we can help you achieve your digital marketing goals.
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Form & Info -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
          <!-- Contact Form -->
          <div>
            <h2 class="text-3xl font-bold mb-6">Send us a Message</h2>
            <form @submit.prevent="handleSubmit" class="space-y-6">
              <div>
                <label for="name" class="block text-sm font-medium text-gray-700 mb-2">Full Name</label>
                <input
                  v-model="form.name"
                  type="text"
                  id="name"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                  placeholder="John Doe"
                />
              </div>

              <div>
                <label for="email" class="block text-sm font-medium text-gray-700 mb-2">Email Address</label>
                <input
                  v-model="form.email"
                  type="email"
                  id="email"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                  placeholder="john@example.com"
                />
              </div>

              <div>
                <label for="phone" class="block text-sm font-medium text-gray-700 mb-2">Phone Number</label>
                <input
                  v-model="form.phone"
                  type="tel"
                  id="phone"
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                  placeholder="+1 (555) 123-4567"
                />
              </div>

              <div>
                <label for="service" class="block text-sm font-medium text-gray-700 mb-2">Service Interested In</label>
                <select
                  v-model="form.service"
                  id="service"
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                >
                  <option value="">Select a service</option>
                  <option value="seo">SEO Optimization</option>
                  <option value="social">Social Media Marketing</option>
                  <option value="ads">Paid Advertising</option>
                  <option value="web">Web Development</option>
                  <option value="branding">Branding & Design</option>
                  <option value="content">Content Marketing</option>
                </select>
              </div>

              <div>
                <label for="message" class="block text-sm font-medium text-gray-700 mb-2">Message</label>
                <textarea
                  v-model="form.message"
                  id="message"
                  rows="5"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary-500 focus:border-transparent transition-all duration-300"
                  placeholder="Tell us about your project..."
                ></textarea>
              </div>

              <BaseButton
                type="submit"
                variant="primary"
                size="lg"
                :loading="isSubmitting"
                class="w-full"
              >
                {{ isSubmitting ? 'Sending...' : 'Send Message' }}
              </BaseButton>
            </form>

            <!-- Success Message -->
            <div v-if="showSuccess" class="mt-6 p-4 bg-green-100 border border-green-400 text-green-700 rounded-lg">
              Thank you for your message! We'll get back to you within 24 hours.
            </div>
          </div>

          <!-- Contact Info -->
          <div>
            <h2 class="text-3xl font-bold mb-6">Get in Touch</h2>
            
            <div class="space-y-6">
              <BaseCard hover class="p-6">
                <div class="flex items-start">
                  <div class="w-12 h-12 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mr-4 flex-shrink-0">
                    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                    </svg>
                  </div>
                  <div>
                    <h3 class="font-semibold text-lg mb-1">Office Address</h3>
                    <p class="text-gray-600">123 Business Ave, Suite 100<br>New York, NY 10001</p>
                  </div>
                </div>
              </BaseCard>

              <BaseCard hover class="p-6">
                <div class="flex items-start">
                  <div class="w-12 h-12 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mr-4 flex-shrink-0">
                    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
                    </svg>
                  </div>
                  <div>
                    <h3 class="font-semibold text-lg mb-1">Phone</h3>
                    <a class="text-gray-600 hover:text-primary-600 transition-colors duration-200" href="tel:+15551234567">+1 (555) 123-4567</a>
                    <p class="text-gray-600">Mon-Fri: 9AM-6PM EST</p>
                  </div>
                </div>
              </BaseCard>

              <BaseCard hover class="p-6">
                <div class="flex items-start">
                  <div class="w-12 h-12 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mr-4 flex-shrink-0">
                    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
                    </svg>
                  </div>
                  <div>
                    <h3 class="font-semibold text-lg mb-1">Email</h3>
                    <a class="text-gray-600 hover:text-primary-600 transition-colors duration-200 block" href="mailto:hello@digitalpro.com">hello@digitalpro.com</a>
                    <a class="text-gray-600 hover:text-primary-600 transition-colors duration-200 block" href="mailto:support@digitalpro.com">support@digitalpro.com</a>
                  </div>
                </div>
              </BaseCard>
            </div>

            <!-- Social Media -->
            <div class="mt-8">
              <h3 class="font-semibold text-lg mb-4">Follow Us</h3>
              <div class="flex space-x-4">
                <a href="#" class="w-12 h-12 bg-gray-100 rounded-full flex items-center justify-center hover:bg-primary-600 hover:text-white transition-all duration-300">
                  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                  </svg>
                </a>
                <a href="#" class="w-12 h-12 bg-gray-100 rounded-full flex items-center justify-center hover:bg-primary-600 hover:text-white transition-all duration-300">
                  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
                  </svg>
                </a>
                <a href="#" class="w-12 h-12 bg-gray-100 rounded-full flex items-center justify-center hover:bg-primary-600 hover:text-white transition-all duration-300">
                  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Map Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl font-bold text-center mb-12">Find Us</h2>
        <div class="bg-gray-300 rounded-xl h-96 flex items-center justify-center">
          <div class="text-center">
            <svg class="w-16 h-16 text-gray-500 mx-auto mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
            </svg>
            <p class="text-gray-600 text-lg">Interactive Map</p>
            <p class="text-gray-500">123 Business Ave, Suite 100, New York, NY</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import BaseCard from '@/components/ui/BaseCard.vue'
import BaseButton from '@/components/ui/BaseButton.vue'

const isSubmitting = ref(false)
const showSuccess = ref(false)

const form = ref({
  name: '',
  email: '',
  phone: '',
  service: '',
  message: ''
})

const handleSubmit = async () => {
  isSubmitting.value = true
  
  // Simulate API call
  await new Promise(resolve => setTimeout(resolve, 2000))
  
  isSubmitting.value = false
  showSuccess.value = true
  
  // Reset form
  form.value = {
    name: '',
    email: '',
    phone: '',
    service: '',
    message: ''
  }
  
  // Hide success message after 5 seconds
  setTimeout(() => {
    showSuccess.value = false
  }, 5000)
}

onMounted(() => {
  // Animate form elements
  gsap.utils.toArray('form > div').forEach((element: any, index: number) => {
    gsap.fromTo(element, 
      { opacity: 0, x: -30 },
      {
        opacity: 1,
        x: 0,
        duration: 0.6,
        delay: index * 0.1,
        ease: "power2.out"
      }
    )
  })
  
  // Animate contact cards
  gsap.utils.toArray('.space-y-6 > div').forEach((card: any, index: number) => {
    gsap.fromTo(card,
      { opacity: 0, x: 30 },
      {
        opacity: 1,
        x: 0,
        duration: 0.6,
        delay: index * 0.1,
        ease: "power2.out"
      }
    )
  })
})
</script>
