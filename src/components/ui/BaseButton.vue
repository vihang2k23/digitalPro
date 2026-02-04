<template>
  <button
    :class="buttonClasses"
    :disabled="disabled"
    @click="$emit('click', $event)"
    class="inline-flex items-center justify-center font-semibold rounded-lg transition-all duration-300 transform focus:outline-none focus:ring-2 focus:ring-offset-2"
    :type="type"
  >
    <svg v-if="loading" class="animate-spin -ml-1 mr-2 h-5 w-5" fill="none" viewBox="0 0 24 24">
      <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
      <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
    </svg>
    
    <span
      v-if="typeof icon === 'string' && icon.trim().startsWith('<svg') && !loading"
      v-html="icon"
      class="w-5 h-5"
      :class="iconPosition === 'left' ? 'mr-2' : 'ml-2'"
    />
    <component
      v-else-if="icon && !loading"
      :is="icon"
      class="w-5 h-5"
      :class="iconPosition === 'left' ? 'mr-2' : 'ml-2'"
    />
    
    <span :class="{ 'opacity-50': loading }">
      <slot />
    </span>
  </button>
</template>

<script setup lang="ts">
import { computed } from 'vue'

interface Props {
  variant?: 'primary' | 'secondary' | 'outline' | 'ghost' | 'danger'
  size?: 'sm' | 'md' | 'lg'
  disabled?: boolean
  loading?: boolean
  type?: 'button' | 'submit' | 'reset'
  icon?: any
  iconPosition?: 'left' | 'right'
  fullWidth?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'primary',
  size: 'md',
  disabled: false,
  loading: false,
  type: 'button',
  iconPosition: 'left',
  fullWidth: false
})

defineEmits<{
  click: [event: Event]
}>()

const buttonClasses = computed(() => {
  const baseClasses = 'transform hover:scale-105 focus:scale-100'
  
  const sizeClasses = {
    sm: 'px-3 py-1.5 text-sm',
    md: 'px-6 py-3 text-base',
    lg: 'px-8 py-4 text-lg'
  }
  
  const variantClasses = {
    primary: 'bg-primary-600 hover:bg-primary-700 text-white hover:shadow-lg focus:ring-primary-500',
    secondary: 'bg-secondary-600 hover:bg-secondary-700 text-white hover:shadow-lg focus:ring-secondary-500',
    outline: 'border-2 border-primary-600 text-primary-600 hover:bg-primary-600 hover:text-white focus:ring-primary-500',
    ghost: 'text-primary-600 hover:bg-primary-50 focus:ring-primary-500',
    danger: 'bg-red-600 hover:bg-red-700 text-white hover:shadow-lg focus:ring-red-500'
  }
  
  const disabledClasses = props.disabled || props.loading ? 'opacity-50 cursor-not-allowed transform-none' : ''
  const widthClasses = props.fullWidth ? 'w-full' : ''
  
  return [
    baseClasses,
    sizeClasses[props.size],
    variantClasses[props.variant],
    disabledClasses,
    widthClasses
  ].filter(Boolean).join(' ')
})
</script>
