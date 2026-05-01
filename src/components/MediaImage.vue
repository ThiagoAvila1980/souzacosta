<template>
  <!-- Componente de imagem com skeleton para melhorar percepção de carregamento -->
  <div class="media-shell" :class="{ 'is-loaded': isLoaded }">
    <div class="media-skeleton" aria-hidden="true"></div>
    <img
      :src="src"
      :alt="alt"
      :loading="loading"
      :class="imgClass"
      @load="isLoaded = true"
      @error="isLoaded = true"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'

// API mínima para reaproveitar o componente em diferentes blocos de mídia.
defineProps({
  src: { type: String, required: true },
  alt: { type: String, default: '' },
  loading: { type: String, default: 'lazy' },
  imgClass: { type: String, default: '' }
})

const isLoaded = ref(false)
</script>
