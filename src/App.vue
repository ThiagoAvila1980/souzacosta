<template>
  <div class="min-h-screen">
    <SiteHeader />
    <div class="reveal"><HeroSection /></div>
    <div class="reveal"><ServicesSection /></div>
    <div class="reveal"><DifferentialsSection /></div>
    <div class="reveal"><TestimonialsSection /></div>
    <div class="reveal"><SiteFooter /></div>
    <a
      href="https://wa.me/55116792240786?text=Ol%C3%A1%2C%20quero%20agendar%20na%20Borracharia%20SouzaCosta%2E"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="Falar no WhatsApp"
      class="whatsapp-float md:hidden"
    >
      <i class="pi pi-whatsapp"></i>
    </a>
  </div>
</template>

<script setup>
import { onBeforeUnmount, onMounted } from 'vue'
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import DifferentialsSection from './components/DifferentialsSection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import SiteFooter from './components/SiteFooter.vue'

let observer

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.15 }
  )

  document.querySelectorAll('.reveal').forEach((el) => observer.observe(el))
})

onBeforeUnmount(() => {
  if (observer) observer.disconnect()
})
</script>
