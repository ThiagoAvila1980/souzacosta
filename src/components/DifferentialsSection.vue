<template>
  <!-- Seção de diferenciais com prova visual em carrossel -->
  <section id="diferenciais" class="py-16 md:py-24 blue-gradient-soft">
    <div class="container-max">
      <SectionHeader
        title="Por que escolher a SouzaCosta"
        lead="Agilidade, qualidade e conforto em cada atendimento."
      />

      <!-- Três pilares principais de confiança da empresa -->
      <div class="grid md:grid-cols-3 gap-4 mt-10">
        <Card v-for="item in differentials" :key="item.title" class="service-card text-center">
          <template #content>
            <div class="w-14 h-14 rounded-full bg-blue-100 text-blue-800 mx-auto grid place-items-center text-xl">
              <i :class="item.icon"></i>
            </div>
            <h3 class="text-xl font-bold text-slate-900 mt-4">{{ item.title }}</h3>
            <p class="text-slate-600 mt-2">{{ item.text }}</p>
          </template>
        </Card>
      </div>

      <div class="mt-12">
        <h3 class="text-2xl font-bold text-slate-900 text-center">Serviço de Qualidade</h3>
        <!-- Carrossel com imagens reais dos serviços -->
        <Carousel
          :value="beforeAfter"
          :numVisible="1"
          :numScroll="1"
          circular
          class="mt-6 max-w-3xl mx-auto"
        >
          <template #item="{ data }">
            <div class="rounded-2xl overflow-hidden border border-blue-100 bg-white shadow-sm">
              <MediaImage
                :src="data.image"
                :alt="data.alt"
                loading="lazy"
                img-class="w-full h-64 md:h-80 object-cover"
              />
            </div>
          </template>
        </Carousel>
      </div>
    </div>
  </section>
</template>

<script setup>
import Card from 'primevue/card'
import Carousel from 'primevue/carousel'
import SectionHeader from './SectionHeader.vue'
import MediaImage from './MediaImage.vue'
import image01 from '../../images/image01.jpg'
import image02 from '../../images/image02.jpeg'
import image03 from '../../images/image03.jpeg'
import image04 from '../../images/image04.jpg'

const differentials = [
  {
    icon: 'pi pi-bolt',
    title: 'Atendimento rápido',
    text: 'Processos otimizados para você resolver tudo sem demora.'
  },
  {
    icon: 'pi pi-verified',
    title: 'Garantia no serviço',
    text: 'Compromisso com acabamento e suporte para sua tranquilidade.'
  },
  {
    icon: 'pi pi-calendar',
    title: 'Mais de 12 anos',
    text: 'Experiência comprovada com centenas de clientes atendidos.'
  }
]

// Lista de imagens exibidas no carrossel da seção.
const beforeAfter = [
  {
    alt: 'Serviço de borracharia com montagem de pneu',
    image: image01
  },
  {
    alt: 'Estoque de pneus em atendimento',
    image: image02
  },
  {
    alt: 'Troca de pneu em oficina',
    image: image03
  },
  {
    alt: 'Serviço técnico com pneu em máquina',
    image: image04
  }
]
</script>
