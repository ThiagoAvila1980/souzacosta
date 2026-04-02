<template>
  <header class="sticky top-0 z-30 border-b border-blue-100 glass-nav">
    <div class="container-max h-[72px] flex items-center justify-between">
      <a href="#" class="flex items-center gap-3">
        <img
          src="/images/tire-minimal.svg"
          alt="Ícone de pneu"
          class="h-10 md:h-11 w-10 md:w-11"
          loading="eager"
        />
        <strong class="text-blue-950 text-base md:text-lg tracking-tight">Borracharia Sousa Costa</strong>
      </a>

      <nav class="hidden md:flex items-center gap-7 text-sm font-medium text-slate-700">
        <a href="#servicos" class="hover:text-blue-700">Serviços</a>
        <a href="#diferenciais" class="hover:text-blue-700">Diferenciais</a>
        <a href="#depoimentos" class="hover:text-blue-700">Depoimentos</a>
        <a href="#contato" class="hover:text-blue-700">Contato</a>
      </nav>

      

      <Button
        icon="pi pi-bars"
        text
        rounded
        aria-label="Abrir menu"
        class="md:!hidden !text-blue-900"
        @click="visible = true"
      />
    </div>

    <Drawer v-model:visible="visible" position="right" header="SouzaCosta">
      <nav class="flex flex-col gap-2 text-slate-700">
        <a href="#servicos" class="menu-link" @click="visible = false">Serviços</a>
        <a href="#diferenciais" class="menu-link" @click="visible = false">Diferenciais</a>
        <a href="#depoimentos" class="menu-link" @click="visible = false">Depoimentos</a>
        <a href="#contato" class="menu-link" @click="visible = false">Contato</a>
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
</script>
