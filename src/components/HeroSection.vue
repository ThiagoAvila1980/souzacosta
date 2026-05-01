<template>
  <!-- Hero: proposta de valor, CTAs principais e mídia de destaque -->
  <section id="home" class="blue-gradient relative overflow-hidden">
    <!-- MOBILE: 1 coluna por padrão | WEB: 2 colunas no breakpoint lg -->
    <div class="container-max py-14 md:py-24 grid lg:grid-cols-2 gap-10 items-center">
      <div>
      <p class="hero-kicker uppercase tracking-[0.14em] font-bold text-xs mb-4">
        Borracharia e Lava Jato SouzaCosta
      </p>
      <h1 class="hero-title text-3xl md:text-6xl font-extrabold leading-tight max-w-4xl">
        Seu carro novo de novo e pronto para a estrada
      </h1>
      <p class="hero-description text-base md:text-lg mt-5 max-w-2xl">
        Serviços de borracharia, vulcanização, remendos, troca de pneus, pneus novos e
        seminovos, rodízio de pneus e outros serviços.
      </p>
      <div class="mt-5 flex flex-wrap gap-2">
        <span class="badge-pill"><i class="pi pi-bolt"></i> Atendimento rápido</span>
        <span class="badge-pill"><i class="pi pi-verified"></i> Garantia no serviço</span>
        <span class="badge-pill"><i class="pi pi-calendar"></i> Mais de 12 anos</span>
      </div>
      <p class="hero-rating mt-4 font-semibold text-sm md:text-base">
        <i class="pi pi-star-fill text-amber-400 mr-1"></i>
        4,9 no Google <span class="hero-rating-sub font-medium">(287 avaliações)</span>
      </p>
      <div class="mt-8 flex flex-wrap gap-3">
        <Button
          as="a"
          href="https://wa.me/55116792240786?text=Ol%C3%A1%2C%20quero%20agendar%20na%20Borracharia%20SouzaCosta%2E"
          target="_blank"
          rel="noopener noreferrer"
          label="Agendar via WhatsApp"
          icon="pi pi-whatsapp"
          class="brand-primary"
        />
        <Button
          as="a"
          href="#mapa"
          label="Ver Localização"
          severity="secondary"
          outlined
          class="brand-outline"
        />
      </div>
      </div>
      <!-- Bloco de mídia com vídeo institucional -->
      <div class="relative w-full max-w-2xl lg:justify-self-end">
        <div class="aspect-video rounded-2xl overflow-hidden border border-blue-200/40 shadow-2xl shadow-black/30 bg-slate-900">
          <video
            ref="heroVideoEl"
            class="w-full h-full object-contain"
            autoplay
            :muted="isMuted"
            loop
            playsinline
            preload="metadata"
            aria-label="Apresentacao da SouzaCosta"
          >
            <source :src="heroVideo" type="video/mp4" />
          </video>
        </div>
        <!-- Controle simples para alternar entre áudio ligado e mudo -->
        <button
          type="button"
          class="absolute right-3 bottom-3 rounded-full px-3 py-2 text-sm font-semibold bg-black/65 text-white border border-white/30 hover:bg-black/75 transition-colors"
          @click="toggleMuted"
        >
          <i :class="isMuted ? 'pi pi-volume-off mr-2' : 'pi pi-volume-up mr-2'"></i>
          {{ isMuted ? 'Sem som' : 'Com som' }}
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import Button from 'primevue/button'
import heroVideo from '../../images/apresentacao.mp4'

const isMuted = ref(true)
const heroVideoEl = ref(null)

const toggleMuted = async () => {
  // Mantém o estado visual sincronizado com a propriedade real do vídeo.
  isMuted.value = !isMuted.value
  if (heroVideoEl.value) {
    heroVideoEl.value.muted = isMuted.value
    try {
      await heroVideoEl.value.play()
    } catch {
      // Ignora bloqueio de autoplay em alguns navegadores.
    }
  }
}
</script>
