<script setup lang="ts">
import type { Gericht } from '@/types/gericht'

const gerichte: Gericht[] = [
  { name: 'Haferflocken mit Banane', kcal: 350 },
  { name: 'Hähnchen mit Reis', kcal: 620 },
  { name: 'Griechischer Salat', kcal: 280 },
]
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
