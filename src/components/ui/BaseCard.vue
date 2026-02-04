<template>
  <div 
    :class="cardClasses"
    @mouseenter="isHovered = true"
    @mouseleave="isHovered = false"
    ref="cardRef"
  >
    <div v-if="$slots.header" class="p-6 border-b border-gray-200">
      <slot name="header" />
    </div>
    
    <div :class="bodyClasses">
      <slot />
    </div>
    
    <div v-if="$slots.footer" class="p-6 border-t border-gray-200 bg-gray-50">
      <slot name="footer" />
    </div>
    
    <!-- Animated gradient border effect -->
    <div v-if="animatedBorder" class="absolute inset-0 rounded-xl bg-gradient-to-r from-primary-600 via-secondary-600 to-primary-600 opacity-0 group-hover:opacity-100 transition-opacity duration-500 -z-10"></div>
    <div v-if="animatedBorder" class="absolute inset-[2px] bg-white rounded-xl -z-10"></div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'
import { gsap } from 'gsap'

interface Props {
  variant?: 'default' | 'outlined' | 'elevated' | 'glass'
  padding?: 'none' | 'sm' | 'md' | 'lg'
  rounded?: 'none' | 'sm' | 'md' | 'lg' | 'xl'
  shadow?: 'none' | 'sm' | 'md' | 'lg' | 'xl'
  hover?: boolean
  animatedBorder?: boolean
  animationDelay?: number
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'default',
  padding: 'md',
  rounded: 'lg',
  shadow: 'md',
  hover: true,
  animatedBorder: false,
  animationDelay: 0
})

const slots = defineSlots()
const cardRef = ref<HTMLElement>()
const isHovered = ref(false)

const cardClasses = computed(() => {
  const baseClasses = 'relative transition-all duration-300'
  
  const variantClasses = {
    default: 'bg-white',
    outlined: 'bg-white border border-gray-200',
    elevated: 'bg-white',
    glass: 'bg-white/80 backdrop-blur-md border border-white/20'
  }
  
  const paddingClasses = {
    none: '',
    sm: 'p-4',
    md: 'p-6',
    lg: 'p-8'
  }
  
  const roundedClasses = {
    none: '',
    sm: 'rounded-sm',
    md: 'rounded-md',
    lg: 'rounded-lg',
    xl: 'rounded-xl'
  }
  
  const shadowClasses = {
    none: '',
    sm: 'shadow-sm',
    md: 'shadow-md',
    lg: 'shadow-lg',
    xl: 'shadow-xl'
  }
  
  const hoverClasses = props.hover ? 'card-hover group cursor-pointer' : ''
  
  return [
    baseClasses,
    variantClasses[props.variant],
    paddingClasses[props.padding],
    roundedClasses[props.rounded],
    shadowClasses[props.shadow],
    hoverClasses
  ].filter(Boolean).join(' ')
})

const bodyClasses = computed(() => {
  if (slots?.header || slots?.footer) {
    const paddingMap = {
      none: '',
      sm: 'p-4',
      md: 'p-6',
      lg: 'p-8'
    }
    return paddingMap[props.padding]
  }
  return ''
})

onMounted(() => {
  if (cardRef.value && props.animationDelay > 0) {
    gsap.fromTo(cardRef.value, 
      {
        opacity: 0,
        y: 30,
        scale: 0.95
      },
      {
        opacity: 1,
        y: 0,
        scale: 1,
        duration: 0.6,
        delay: props.animationDelay,
        ease: "power2.out"
      }
    )
  }
})
</script>
