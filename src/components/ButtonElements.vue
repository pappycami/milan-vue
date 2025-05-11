<template>
  <button @click="$emit('click')" class="btn">
    <slot />
  </button>
</template>

<script setup lang="ts">
defineEmits(['click'])
</script>

<style scoped>
.btn {
  background: #42b883;
  color: white;
  padding: 0.5em 1em;
  border-radius: 8px;
  cursor: pointer;
}
</style>
