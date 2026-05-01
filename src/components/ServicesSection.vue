<template>
  <!-- Seção de serviços organizada em cards por categoria -->
  <section id="servicos" class="py-16 md:py-24 bg-white">
    <div class="container-max">
      <SectionHeader
        title="Nossos serviços"
        lead="Tudo o que seu veículo precisa para rodar com segurança e visual impecável."
      />

      <div class="grid md:grid-cols-2 gap-6 mt-10">
        <Card class="service-card">
          <template #title>
            <div class="flex items-center gap-3">
              <i class="pi pi-car text-2xl text-blue-700"></i>
              <span class="text-2xl font-bold text-slate-900">Lava Jato</span>
            </div>
          </template>
          <template #content>
            <ul class="list-disc pl-5 text-slate-600 space-y-2">
              <li>Lavagem simples</li>
              <li>Lavagem completa</li>
              <li>Higienização interna</li>
              <li>Polimento</li>
              <li>Estética automotiva</li>
            </ul>
          </template>
        </Card>

        <Card class="service-card">
          <template #title>
            <div class="flex items-center gap-3">
              <i class="pi pi-cog text-2xl text-blue-700"></i>
              <span class="text-2xl font-bold text-slate-900">Borracharia</span>
            </div>
          </template>
          <template #content>
            <ul class="list-disc pl-5 text-slate-600 space-y-2">
              <li>Conserto de pneus</li>
              <li>Remendos e reparos rápidos</li>
              <li>Troca de pneus</li>
              <li>Balanceamento</li>
              <li>Rodízio de pneus</li>
              <li>Vulcanização</li>
              <li>Venda de pneus novos</li>
              <li>Venda de pneus seminovos</li>
            </ul>
          </template>
        </Card>
      </div>
    </div>
  </section>
</template>

<script setup>
import Card from 'primevue/card'
import SectionHeader from './SectionHeader.vue'
</script>
