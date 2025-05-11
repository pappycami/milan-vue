<template>
  <DefaultLayout>
    <template #header>
      <h1>Bienvenue 👋</h1>
    </template>

    <template #default>
      <p>Compteur : {{ counter.count }}</p>
      <Button @click="counter.increment">+1</Button>
      <Button @click="counter.reset">Reset</Button>
    </template>
  </DefaultLayout>
</template>

<script setup lang="ts">
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import Button from '@/components/Button.vue'
import { useCounter } from '@/composables/useCounter.js'

const counter = useCounter()
</script>
