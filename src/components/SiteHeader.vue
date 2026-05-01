<template>
  <!-- Cabeçalho fixo com navegação âncora para as seções -->
  <header class="sticky top-0 z-30 border-b border-blue-200/30 glass-nav">
    <div class="container-max h-[72px] flex items-center justify-between">
      <a href="#" class="flex items-center gap-3">
        <img
          src="/images/tire-minimal.svg"
          alt="Ícone de pneu"
          class="h-10 md:h-11 w-10 md:w-11"
          loading="eager"
        />
        <strong class="text-blue-50 text-base md:text-lg tracking-tight">Borracharia Sousa Costa</strong>
      </a>

      <!-- WEB (desktop): menu horizontal visível a partir de md -->
      <nav class="hidden md:flex items-center gap-7 text-sm font-medium">
        <a href="#servicos" class="header-link">Serviços</a>
        <a href="#diferenciais" class="header-link">Diferenciais</a>
        <a href="#depoimentos" class="header-link">Depoimentos</a>
        <a href="#contato" class="header-link">Contato</a>
      </nav>

      

      <!-- MOBILE: botão hambúrguer visível apenas abaixo de md -->
      <Button
        icon="pi pi-bars"
        text
        rounded
        aria-label="Abrir menu"
        class="md:!hidden !text-blue-50"
        @click="visible = true"
      />
    </div>

    <!-- MOBILE: menu lateral (Drawer) para navegação em telas pequenas -->
    <Drawer v-model:visible="visible" position="right" header="SouzaCosta">
      <nav class="flex flex-col gap-2 text-slate-700">
        <a href="#servicos" class="menu-link" @click.prevent="scrollToSection('servicos')">Serviços</a>
        <a href="#diferenciais" class="menu-link" @click.prevent="scrollToSection('diferenciais')">Diferenciais</a>
        <a href="#depoimentos" class="menu-link" @click.prevent="scrollToSection('depoimentos')">Depoimentos</a>
        <a href="#contato" class="menu-link" @click.prevent="scrollToSection('contato')">Contato</a>
      </nav>
      <Button
        as="a"
        href="https://wa.me/55116792240786?text=Ol%C3%A1%2C%20quero%20agendar%20na%20Borracharia%20SouzaCosta%2E"
        target="_blank"
        rel="noopener noreferrer"
        label="Agendar via WhatsApp"
        icon="pi pi-whatsapp"
        class="brand-primary w-full mt-5"
      />
    </Drawer>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import Button from 'primevue/button'
import Drawer from 'primevue/drawer'

const visible = ref(false)

// Ajuste fino do ponto onde cada seção deve "parar" no mobile.
// Aumente o valor para descer mais a seção; diminua para subir.
const MOBILE_SCROLL_OFFSET = {
  servicos: 88,
  diferenciais: 88,
  depoimentos: 88,
  contato: 88
}

const scrollToSection = (sectionId) => {
  const target = document.getElementById(sectionId)
  if (!target) {
    visible.value = false
    return
  }

  const offset = MOBILE_SCROLL_OFFSET[sectionId] ?? 88
  const targetTop = target.getBoundingClientRect().top + window.scrollY - offset

  window.scrollTo({
    top: Math.max(0, targetTop),
    behavior: 'smooth'
  })

  visible.value = false
}
</script>
