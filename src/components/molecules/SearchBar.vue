<script setup lang="ts">
import { ref } from 'vue'
import BaseButton from '@components/atoms/BaseButton.vue'

interface SearchBarProps {
  placeholder?: string
}

const props = withDefaults(defineProps<SearchBarProps>(), {
  placeholder: 'Rechercher...'
})

const searchQuery = ref('')

const emit = defineEmits<{
  (e: 'search', query: string): void
}>()

const handleSearch = () => {
  emit('search', searchQuery.value)
}
</script>

<template>
  <div class="search-bar">
    <input
      v-model="searchQuery"
      type="text"
      :placeholder="placeholder"
      class="search-input"
      @keyup.enter="handleSearch"
    />
    <BaseButton
      variant="primary"
      size="medium"
      @click="handleSearch"
    >
      Rechercher
    </BaseButton>
  </div>
</template>

<style scoped>
.search-bar {
  display: flex;
  gap: 0.5rem;
  max-width: 600px;
  width: 100%;
}

.search-input {
  flex: 1;
  padding: 0.75rem 1rem;
  border: 2px solid #e5e7eb;
  border-radius: 6px;
  font-size: 1rem;
  outline: none;
  transition: border-color 0.2s ease;
}

.search-input:focus {
  border-color: #3b82f6;
}
</style>