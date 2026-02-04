<template>
  <div class="min-h-screen">
    <!-- Hero Section -->
    <section class="py-20 bg-gradient-to-br from-primary-50 via-white to-secondary-50">
      <div class="container mx-auto px-4">
        <div class="text-center max-w-4xl mx-auto">
          <h1 class="text-4xl md:text-6xl font-bold mb-6">
            <span class="gradient-text">Our Services</span>
          </h1>
          <p class="text-xl text-gray-600">
            Comprehensive digital marketing solutions designed to accelerate your business growth
          </p>
        </div>
      </div>
    </section>

    <!-- Services Grid -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <BaseCard 
            v-for="(service, index) in allServices" 
            :key="service.id"
            hover
            animated-border
            :animation-delay="index * 0.1"
            class="text-center group"
          >
            <div class="w-20 h-20 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mx-auto mb-6 transform group-hover:scale-110 transition-transform duration-300">
              <component :is="service.icon" class="w-10 h-10 text-white" />
            </div>
            <h3 class="text-2xl font-bold mb-4">{{ service.title }}</h3>
            <p class="text-gray-600 mb-6 leading-relaxed">{{ service.description }}</p>
            
            <!-- Features List -->
            <ul class="text-left mb-6 space-y-2">
              <li v-for="feature in service.features" :key="feature" class="flex items-center text-gray-600">
                <div class="w-2 h-2 bg-primary-600 rounded-full mr-3"></div>
                {{ feature }}
              </li>
            </ul>
            
            <BaseButton variant="primary" class="w-full" @click="router.push('/contact')">
              Learn More
            </BaseButton>
          </BaseCard>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold mb-4">Our Process</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">
            We follow a proven methodology to ensure your success
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
          <div v-for="(step, index) in process" :key="step.id" class="text-center">
            <div class="relative mb-6">
              <div class="w-16 h-16 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mx-auto text-white font-bold text-xl">
                {{ index + 1 }}
              </div>
              <div v-if="index < process.length - 1" class="hidden md:block absolute top-8 left-full w-full h-0.5 bg-gradient-to-r from-primary-600 to-secondary-600"></div>
            </div>
            <h3 class="text-lg font-semibold mb-2">{{ step.title }}</h3>
            <p class="text-gray-600">{{ step.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-20 bg-gradient-to-r from-primary-600 to-secondary-600 text-white">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-4">Ready to Get Started?</h2>
        <p class="text-xl mb-8 max-w-2xl mx-auto">
          Let's discuss how our services can help you achieve your business goals
        </p>
        <BaseButton variant="secondary" size="lg" class="text-lg" @click="router.push('/contact')">
          Schedule a Free Consultation
        </BaseButton>
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
import WebIcon from '@/components/icons/WebIcon.vue'
import BrandIcon from '@/components/icons/BrandIcon.vue'
import ContentIcon from '@/components/icons/ContentIcon.vue'

const router = useRouter()

const allServices = ref([
  {
    id: 1,
    title: 'SEO Optimization',
    description: 'Improve your search rankings and drive organic traffic with our comprehensive SEO strategies.',
    icon: SearchIcon,
    features: [
      'Keyword Research & Analysis',
      'On-Page SEO Optimization',
      'Technical SEO Audits',
      'Link Building Campaigns',
      'Local SEO Optimization'
    ]
  },
  {
    id: 2,
    title: 'Social Media Marketing',
    description: 'Build brand awareness and engage your audience across all social media platforms.',
    icon: SocialIcon,
    features: [
      'Social Media Strategy',
      'Content Creation & Management',
      'Community Engagement',
      'Social Media Advertising',
      'Analytics & Reporting'
    ]
  },
  {
    id: 3,
    title: 'Paid Advertising',
    description: 'Maximize your ROI with targeted Google Ads and social media advertising campaigns.',
    icon: AdsIcon,
    features: [
      'Google Ads Management',
      'Facebook & Instagram Ads',
      'LinkedIn Advertising',
      'Retargeting Campaigns',
      'A/B Testing & Optimization'
    ]
  },
  {
    id: 4,
    title: 'Web Development',
    description: 'Create stunning, high-performance websites that convert visitors into customers.',
    icon: WebIcon,
    features: [
      'Responsive Web Design',
      'E-commerce Development',
      'Website Optimization',
      'CMS Integration',
      'Website Maintenance'
    ]
  },
  {
    id: 5,
    title: 'Branding & Design',
    description: 'Develop a strong brand identity that resonates with your target audience.',
    icon: BrandIcon,
    features: [
      'Brand Strategy Development',
      'Logo Design & Identity',
      'Brand Guidelines',
      'Marketing Materials',
      'Visual Branding'
    ]
  },
  {
    id: 6,
    title: 'Content Marketing',
    description: 'Create compelling content that attracts, engages, and converts your audience.',
    icon: ContentIcon,
    features: [
      'Content Strategy & Planning',
      'Blog Writing & Management',
      'Video Content Production',
      'Email Marketing',
      'Content Distribution'
    ]
  }
])

const process = ref([
  {
    id: 1,
    title: 'Discovery',
    description: 'We learn about your business, goals, and target audience.'
  },
  {
    id: 2,
    title: 'Strategy',
    description: 'We develop a customized digital marketing strategy tailored to your needs.'
  },
  {
    id: 3,
    title: 'Implementation',
    description: 'We execute the strategy with precision and attention to detail.'
  },
  {
    id: 4,
    title: 'Optimization',
    description: 'We continuously monitor, analyze, and optimize for better results.'
  }
])

onMounted(() => {
  // Animate service cards on scroll
  gsap.utils.toArray('.group').forEach((card: any, index: number) => {
    gsap.fromTo(card,
      { opacity: 0, y: 50 },
      {
        opacity: 1,
        y: 0,
        duration: 0.6,
        delay: index * 0.1,
        ease: "power2.out"
      }
    )
  })
})
</script>
