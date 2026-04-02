<template>
  <footer id="contato" class="text-white py-14" style="background-color: #4392de">
    <div class="container-max">
      <div class="grid lg:grid-cols-3 gap-8">
        <div>
          <div class="flex items-center gap-3">
            <img
              src="/images/tire-minimal.svg"
              alt="Ícone de pneu"
              class="h-10 md:h-11 w-10 md:w-11"
              loading="lazy"
            />
          </div>
          <p class="text-white/95 mt-4 max-w-xs">
            Borracharia e Lava Jato - seu carro novo de novo e pronto para a estrada.
          </p>
          <p class="text-white/95 mt-3">
            <i class="pi pi-map-marker mr-2"></i>
            Av. Hiroshima, 1490 - Carandá Bosque, Campo Grande - MS
          </p>
          <p class="text-white/95 mt-2">
            <i class="pi pi-envelope mr-2"></i>
            <a href="mailto:msc-garrincha@hotmail.com" class="underline">
              msc-garrincha@hotmail.com
            </a>
          </p>
          <div class="flex gap-3 mt-5 text-lg">
            <a
              href="https://www.instagram.com/souzacostam216/"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="Instagram SouzaCosta"
              class="w-10 h-10 rounded-lg bg-white/15 grid place-items-center"
            >
              <i class="pi pi-instagram"></i>
            </a>
            <a
              href="https://www.facebook.com/marcelo.sousacosta?locale=pt_BR"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="Facebook SouzaCosta"
              class="w-10 h-10 rounded-lg bg-white/15 grid place-items-center"
            >
              <i class="pi pi-facebook"></i>
            </a>
            <a
              href="https://wa.me/55116792240786?text=Ol%C3%A1%2C%20quero%20agendar%20na%20Borracharia%20SouzaCosta%2E"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="WhatsApp"
              class="w-10 h-10 rounded-lg bg-white/15 grid place-items-center"
            >
              <i class="pi pi-whatsapp"></i>
            </a>
          </div>
        </div>

        <div>
          <h3 class="text-xl font-bold">Horário de funcionamento</h3>
          <ul class="mt-4 space-y-2 text-white/95">
            <li class="flex justify-between border-b border-white/15 pb-2">
              <span>Segunda a sexta</span>
              <strong>07:15 - 17:30h</strong>
            </li>
            <li class="flex justify-between border-b border-white/15 pb-2">
              <span>Sábado</span>
              <strong>08:00 - 12:00h</strong>
            </li>
            <li class="flex justify-between border-b border-white/15 pb-2">
              <span>Domingo</span>
              <strong>Fechado</strong>
            </li>
          </ul>
        </div>

        <div id="mapa">
          <h3 class="text-xl font-bold">Onde estamos</h3>
          <div class="rounded-xl overflow-hidden mt-4 border border-white/20">
            <iframe
              title="Mapa - Borracharia e Lava Jato SouzaCosta"
              src="https://maps.google.com/maps?q=Av.%20Hiroshima%2C%201490%20-%20Carand%C3%A1%20Bosque%2C%20Campo%20Grande%20-%20MS%2C%2079032-050%2C%20Brasil&z=16&output=embed"
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              class="w-full h-56 border-0"
              allowfullscreen
            ></iframe>
          </div>
          <p class="text-xs text-blue-100/70 mt-2">Av. Hiroshima, 1490 - Carandá Bosque.</p>
        </div>
      </div>

      <p class="text-center text-sm text-white/85 mt-10">
        © {{ year }} Borracharia e Lava Jato SouzaCosta. Todos os direitos reservados.
      </p>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>
