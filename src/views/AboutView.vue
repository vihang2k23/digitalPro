<template>
  <div class="min-h-screen">
    <!-- Hero Section -->
    <section class="py-20 bg-gradient-to-br from-primary-50 via-white to-secondary-50">
      <div class="container mx-auto px-4">
        <div class="text-center max-w-4xl mx-auto">
          <h1 class="text-4xl md:text-6xl font-bold mb-6">
            <span class="gradient-text">About DigitalPro</span>
          </h1>
          <p class="text-xl text-gray-600">
            We're a team of passionate digital marketing experts dedicated to helping businesses thrive in the digital landscape.
          </p>
        </div>
      </div>
    </section>

    <!-- Company Intro -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-3xl font-bold mb-6">Our Story</h2>
            <p class="text-gray-600 mb-4 leading-relaxed">
              Founded in 2018, DigitalPro started with a simple mission: to help businesses navigate the complex world of digital marketing. What began as a small team of passionate marketers has grown into a full-service digital agency serving clients worldwide.
            </p>
            <p class="text-gray-600 mb-6 leading-relaxed">
              We believe in data-driven strategies, creative solutions, and measurable results. Our approach combines cutting-edge technology with human creativity to deliver exceptional outcomes for our clients.
            </p>
            <BaseButton variant="primary" size="lg" @click="scrollToTeam">
              Meet Our Team
            </BaseButton>
          </div>
          <div class="relative">
            <img src="https://picsum.photos/seed/office/600/400.jpg" alt="Our Office" class="rounded-xl shadow-2xl">
            <div class="absolute -bottom-6 -right-6 bg-gradient-to-r from-primary-600 to-secondary-600 text-white p-6 rounded-xl">
              <div class="text-3xl font-bold">5+</div>
              <div class="text-sm">Years of Excellence</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Mission & Vision -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <BaseCard hover class="p-8 text-center">
            <div class="w-16 h-16 bg-gradient-to-r from-primary-600 to-secondary-600 rounded-full flex items-center justify-center mx-auto mb-4">
              <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
              </svg>
            </div>
            <h3 class="text-2xl font-bold mb-4">Our Mission</h3>
            <p class="text-gray-600 leading-relaxed">
              To empower businesses with innovative digital marketing strategies that drive growth, increase brand visibility, and deliver measurable results in an ever-evolving digital landscape.
            </p>
          </BaseCard>
          
          <BaseCard hover class="p-8 text-center">
            <div class="w-16 h-16 bg-gradient-to-r from-secondary-600 to-primary-600 rounded-full flex items-center justify-center mx-auto mb-4">
              <svg class="w-8 h-8 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path>
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"></path>
              </svg>
            </div>
            <h3 class="text-2xl font-bold mb-4">Our Vision</h3>
            <p class="text-gray-600 leading-relaxed">
              To be the leading digital marketing agency known for innovation, integrity, and exceptional client success stories that transform businesses and industries.
            </p>
          </BaseCard>
        </div>
      </div>
    </section>

    <!-- Animated Stats -->
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold mb-4">Our Impact</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">
            Numbers that speak for themselves
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="stat in stats" :key="stat.id" class="text-center">
            <div class="w-20 h-20 bg-gradient-to-r from-primary-100 to-secondary-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <component :is="stat.icon" class="w-10 h-10 text-primary-600" />
            </div>
            <div class="text-4xl font-bold gradient-text mb-2">
              <span ref="statNumbers">{{ stat.prefix }}0</span>{{ stat.suffix }}
            </div>
            <p class="text-gray-600 font-medium">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-4xl font-bold mb-4">Meet Our Team</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">
            The talented people behind your success
          </p>
        </div>
        
        <div id="team" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <BaseCard v-for="member in team" :key="member.id" hover class="text-center">
            <img :src="member.avatar" :alt="member.name" class="w-24 h-24 rounded-full mx-auto mb-4">
            <h3 class="text-lg font-semibold mb-1">{{ member.name }}</h3>
            <p class="text-primary-600 font-medium mb-3">{{ member.role }}</p>
            <p class="text-gray-600 text-sm">{{ member.bio }}</p>
          </BaseCard>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-20 bg-gradient-to-r from-primary-600 to-secondary-600 text-white">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-4">Join Our Success Story</h2>
        <p class="text-xl mb-8 max-w-2xl mx-auto">
          Ready to take your digital marketing to the next level? Let's work together.
        </p>
        <BaseButton variant="secondary" size="lg" class="text-lg" @click="router.push('/contact')">
          Get Started Today
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
import CheckIcon from '@/components/icons/CheckIcon.vue'
import UsersIcon from '@/components/icons/UsersIcon.vue'
import MoneyIcon from '@/components/icons/MoneyIcon.vue'
import TeamIcon from '@/components/icons/TeamIcon.vue'

const router = useRouter()

const statNumbers = ref<HTMLElement[]>([])

const stats = ref([
  {
    id: 1,
    prefix: '',
    suffix: '+',
    label: 'Projects Completed',
    value: 500,
    icon: CheckIcon
  },
  {
    id: 2,
    prefix: '',
    suffix: '+',
    label: 'Happy Clients',
    value: 200,
    icon: UsersIcon
  },
  {
    id: 3,
    prefix: '',
    suffix: 'M+',
    label: 'Revenue Generated',
    value: 50,
    icon: MoneyIcon
  },
  {
    id: 4,
    prefix: '',
    suffix: '+',
    label: 'Team Members',
    value: 25,
    icon: TeamIcon
  }
])

const scrollToTeam = () => {
  const el = document.getElementById('team')
  el?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

const team = ref([
  {
    id: 1,
    name: 'Alex Johnson',
    role: 'CEO & Founder',
    bio: 'Digital marketing expert with 10+ years of experience',
    avatar: 'https://picsum.photos/seed/alex/150/150.jpg'
  },
  {
    id: 2,
    name: 'Sarah Chen',
    role: 'Head of Strategy',
    bio: 'Specialized in data-driven marketing strategies',
    avatar: 'https://picsum.photos/seed/sarah/150/150.jpg'
  },
  {
    id: 3,
    name: 'Mike Davis',
    role: 'Creative Director',
    bio: 'Award-winning designer and brand strategist',
    avatar: 'https://picsum.photos/seed/mike/150/150.jpg'
  },
  {
    id: 4,
    name: 'Emily Wilson',
    role: 'Lead Developer',
    bio: 'Full-stack developer and tech enthusiast',
    avatar: 'https://picsum.photos/seed/emily/150/150.jpg'
  }
])

onMounted(() => {
  // Animate stats numbers
  statNumbers.value.forEach((element: any, index: number) => {
    const stat = stats.value[index]
<<<<<<< HEAD
    if (stat && element) {
=======
    if (stat) {
>>>>>>> 41d97cb98f01823ae0c70dd05801d9da79fbd138
      gsap.to(element, {
        innerHTML: stat.prefix + stat.value + stat.suffix,
        duration: 2,
        delay: index * 0.2,
        ease: "power2.out",
        snap: { innerHTML: 1 }
      })
    }
  })

  // Animate team cards
  gsap.utils.toArray('.text-center').forEach((card: any, index: number) => {
    gsap.fromTo(card,
      { opacity: 0, y: 30 },
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
