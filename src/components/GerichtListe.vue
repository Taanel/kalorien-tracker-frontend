<script setup lang="ts">
import { onMounted, ref } from 'vue'
import type { Gericht } from '@/types/gericht'

const gerichte = ref<Gericht[]>([])

async function ladeGerichte() {
  const baseUrl = import.meta.env.VITE_BACKEND_BASE_URL
  try {
    const response = await fetch(`${baseUrl}/gerichte`)
    gerichte.value = await response.json()
  } catch (error) {
    console.error('Fehler beim Laden der Gerichte:', error)
  }
}

onMounted(ladeGerichte)
</script>

<template>
  <h2>Meine Gerichte</h2>
  <ul>
    <li v-for="gericht in gerichte" :key="gericht.name">
      {{ gericht.name }} - {{ gericht.kcal }} Kalorien
    </li>
  </ul>
</template>

<style scoped></style>
