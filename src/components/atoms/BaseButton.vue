<script setup lang="ts">
interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'outline'
  size?: 'small' | 'medium' | 'large'
  disabled?: boolean
}

withDefaults(defineProps<ButtonProps>(), {
  variant: 'primary',
  size: 'medium',
  disabled: false
})

defineEmits<{
  (e: 'click', event: MouseEvent): void
}>()
</script>

<template>
  <button
    :class="[
      'base-button',
      `base-button--${variant}`,
      `base-button--${size}`,
      { 'base-button--disabled': disabled }
    ]"
    :disabled="disabled"
    @click="$emit('click', $event)"
  >
    <slot />
  </button>
</template>

<style scoped>
.base-button {
  border-radius: 6px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

.base-button--primary {
  background-color: #3b82f6;
  color: white;
  border: none;
}

.base-button--primary:hover {
  background-color: #2563eb;
}

.base-button--secondary {
  background-color: #9ca3af;
  color: white;
  border: none;
}

.base-button--secondary:hover {
  background-color: #6b7280;
}

.base-button--outline {
  background-color: transparent;
  border: 2px solid #3b82f6;
  color: #3b82f6;
}

.base-button--outline:hover {
  background-color: #3b82f6;
  color: white;
}

.base-button--small {
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
}

.base-button--medium {
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
}

.base-button--large {
  padding: 1rem 2rem;
  font-size: 1.125rem;
}

.base-button--disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.base-button--disabled:hover {
  background-color: inherit;
}
</style>