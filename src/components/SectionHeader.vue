<template>
  <!-- Cabeçalho reutilizável para título e descrição curta de cada seção -->
  <header class="text-center">
    <h2 class="section-title">{{ title }}</h2>
    <p v-if="lead" class="section-lead">{{ lead }}</p>
  </header>
</template>

<script setup>
// Props padronizadas para manter consistência entre seções.
defineProps({
  title: {
    type: String,
    required: true
  },
  lead: {
    type: String,
    default: ''
  }
})
</script>
