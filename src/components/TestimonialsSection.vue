<template>
  <section id="depoimentos" class="py-16 md:py-24 bg-white">
    <div class="container-max">
      <SectionHeader
        title="O que nossos clientes dizem"
        lead="Confiança construída com serviço bem feito."
      />
      <div class="google-rating mt-6">
        <span class="stars" aria-hidden="true">★★★★★</span>
        <strong>4,9</strong>
        <span>com base em 287 avaliações no Google</span>
      </div>

      <div class="grid md:grid-cols-3 gap-6 mt-10">
        <Card v-for="item in testimonials" :key="item.name" class="service-card text-center">
          <template #content>
            <Avatar
              :label="item.initials"
              shape="circle"
              size="xlarge"
              class="bg-blue-600 text-white font-bold"
            />
            <p class="text-slate-700 mt-4 italic">"{{ item.text }}"</p>
            <p class="text-blue-900 font-semibold mt-4">{{ item.name }}</p>
          </template>
        </Card>
      </div>
    </div>
  </section>
</template>

<script setup>
import Card from 'primevue/card'
import Avatar from 'primevue/avatar'
import SectionHeader from './SectionHeader.vue'

const testimonials = [
  {
    initials: 'MR',
    name: 'Marina Ribeiro',
    text: 'Atendimento rápido e o carro saiu impecável. Recomendo o lava jato completo.'
  },
  {
    initials: 'CS',
    name: 'Carlos Souza',
    text: 'Consertaram meu pneu na hora e ainda fizeram balanceamento com preço justo.'
  },
  {
    initials: 'AL',
    name: 'Ana Lima',
    text: 'Espaço confortável e equipe muito atenciosa. Virou minha referência.'
  }
]
</script>
