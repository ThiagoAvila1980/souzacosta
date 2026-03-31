<template>
  <header class="text-center">
    <h2 class="section-title">{{ title }}</h2>
    <p v-if="lead" class="section-lead">{{ lead }}</p>
  </header>
</template>

<script setup>
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
