<template>
  <div class="min-h-screen">
    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-primary-50 via-white to-secondary-50">
      <!-- Animated Background -->
      <div class="absolute inset-0 overflow-hidden">
        <div class="absolute top-20 left-20 w-72 h-72 bg-primary-200 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-float"></div>
        <div class="absolute top-40 right-20 w-96 h-96 bg-secondary-200 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-float" style="animation-delay: 2s;"></div>
        <div class="absolute bottom-20 left-1/2 w-80 h-80 bg-primary-300 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-float" style="animation-delay: 4s;"></div>
      </div>
      
      <div class="relative z-10 container mx-auto px-4 text-center">
        <div class="max-w-4xl mx-auto">
          <h1 class="text-5xl md:text-7xl font-bold mb-6">
            <span class="gradient-text">Transform Your Digital</span>
            <br>
            <span class="text-gray-900">Presence Today</span>
          </h1>
          <p class="text-xl md:text-2xl text-gray-600 mb-8 max-w-2xl mx-auto">
            We help businesses grow with cutting-edge digital marketing strategies that deliver real results and measurable ROI.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <BaseButton variant="primary" size="lg" class="text-lg" @click="router.push('/contact')">
              Get Started Now
            </BaseButton>
            <BaseButton variant="outline" size="lg" class="text-lg" @click="router.push('/services')">
              View Our Work
            </BaseButton>
          </div>
        </div>
      </div>
      
      <!-- Scroll Indicator -->
      <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
        <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
      </div>
    </section>

    <!-- Services Preview -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold mb-4">Our Services</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">
            Comprehensive digital marketing solutions tailored to your business needs
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <BaseCard 
            v-for="(service, index) in services" 
            :key="service.id"
            hover
            :animation-delay="index * 0.1"
            class="text-center"
          >
            <div class="w-16 h-16 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mx-auto mb-4">
              <component :is="service.icon" class="w-8 h-8 text-white" />
            </div>
            <h3 class="text-xl font-semibold mb-3">{{ service.title }}</h3>
            <p class="text-gray-600 mb-4">{{ service.description }}</p>
            <router-link :to="'/services'" class="text-primary-600 hover:text-primary-700 font-medium">
              Learn More →
            </router-link>
          </BaseCard>
        </div>
      </div>
    </section>

    <!-- Why Choose Us -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold mb-4">Why Choose Us</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">
            We deliver exceptional results through expertise, innovation, and dedication
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(feature, index) in features" :key="feature.id" class="text-center">
            <BaseCard hover class="h-full">
              <div class="w-20 h-20 bg-gradient-to-r from-primary-100 to-secondary-100 rounded-full flex items-center justify-center mx-auto mb-4">
                <component :is="feature.icon" class="w-10 h-10 text-primary-600" />
              </div>
              <h3 class="text-lg font-semibold mb-2">{{ feature.title }}</h3>
              <p class="text-gray-600">{{ feature.description }}</p>
            </BaseCard>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold mb-4">What Our Clients Say</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">
            Real results from real businesses we've helped grow
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <BaseCard v-for="(testimonial, index) in testimonials" :key="testimonial.id" class="h-full">
            <div class="flex items-center mb-4">
              <img :src="testimonial.avatar" :alt="testimonial.name" class="w-12 h-12 rounded-full mr-4">
              <div>
                <h4 class="font-semibold">{{ testimonial.name }}</h4>
                <p class="text-sm text-gray-600">{{ testimonial.company }}</p>
              </div>
            </div>
            <div class="flex mb-3">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-400" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"></path>
              </svg>
            </div>
            <p class="text-gray-700 italic">"{{ testimonial.content }}"</p>
          </BaseCard>
        </div>
      </div>
    </section>

    <!-- Final CTA -->
    <section class="py-20 bg-gradient-to-r from-primary-600 to-secondary-600 text-white">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-4">Ready to Grow Your Business?</h2>
        <p class="text-xl mb-8 max-w-2xl mx-auto">
          Let's discuss how we can help you achieve your digital marketing goals
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <BaseButton variant="secondary" size="lg" class="text-lg" @click="router.push('/contact')">
            Schedule a Consultation
          </BaseButton>
          <BaseButton
            variant="outline"
            size="lg"
            class="text-lg border-white text-white hover:bg-secondary hover:text-green"
            @click="router.push('/services')"
          >
            View Case Studies
          </BaseButton>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { useRouter } from 'vue-router'
import { gsap } from 'gsap'
import BaseCard from '@/components/ui/BaseCard.vue'
import BaseButton from '@/components/ui/BaseButton.vue'
import SearchIcon from '@/components/icons/SearchIcon.vue'
import SocialIcon from '@/components/icons/SocialIcon.vue'
import AdsIcon from '@/components/icons/AdsIcon.vue'
import CheckIcon from '@/components/icons/CheckIcon.vue'
import UsersIcon from '@/components/icons/UsersIcon.vue'
import LightbulbIcon from '@/components/icons/LightbulbIcon.vue'
import SupportIcon from '@/components/icons/SupportIcon.vue'

const router = useRouter()

const services = ref([
  {
    id: 1,
    title: 'SEO Optimization',
    description: 'Boost your search rankings and drive organic traffic with our proven SEO strategies.',
    icon: SearchIcon
  },
  {
    id: 2,
    title: 'Social Media Marketing',
    description: 'Engage your audience and build brand awareness across all social platforms.',
    icon: SocialIcon
  },
  {
    id: 3,
    title: 'Paid Advertising',
    description: 'Maximize ROI with targeted Google and Meta ad campaigns.',
    icon: AdsIcon
  }
])

const features = ref([
  {
    id: 1,
    title: 'Proven Results',
    description: '500+ successful campaigns with measurable ROI',
    icon: CheckIcon
  },
  {
    id: 2,
    title: 'Expert Team',
    description: 'Certified professionals with 10+ years experience',
    icon: UsersIcon
  },
  {
    id: 3,
    title: 'Custom Strategy',
    description: 'Tailored solutions for your unique business needs',
    icon: LightbulbIcon
  },
  {
    id: 4,
    title: '24/7 Support',
    description: 'Always here to help you succeed',
    icon: SupportIcon
  }
])

const testimonials = ref([
  {
    id: 1,
    name: 'Sarah Johnson',
    company: 'Tech Startup Inc.',
    content: 'Working with DigitalPro transformed our online presence. Our organic traffic increased by 300% in just 6 months!',
    avatar: 'https://picsum.photos/seed/avatar1/100/100.jpg'
  },
  {
    id: 2,
    name: 'Michael Chen',
    company: 'E-commerce Store',
    content: 'The ROI we achieved through their PPC campaigns exceeded our expectations. Highly recommended!',
    avatar: 'https://picsum.photos/seed/avatar2/100/100.jpg'
  },
  {
    id: 3,
    name: 'Emily Davis',
    company: 'Local Restaurant',
    content: 'Their social media strategy helped us reach new customers and increase reservations by 150%.',
    avatar: 'https://picsum.photos/seed/avatar3/100/100.jpg'
  }
])

onMounted(() => {
  // Animate hero elements
  gsap.fromTo('.gradient-text', 
    { opacity: 0, y: 30 },
    { opacity: 1, y: 0, duration: 1, delay: 0.2, ease: "power2.out" }
  )
  
  gsap.fromTo('p.text-xl', 
    { opacity: 0, y: 30 },
    { opacity: 1, y: 0, duration: 1, delay: 0.4, ease: "power2.out" }
  )
  
  gsap.fromTo('.flex.gap-4', 
    { opacity: 0, y: 30 },
    { opacity: 1, y: 0, duration: 1, delay: 0.6, ease: "power2.out" }
  )
})
</script>
