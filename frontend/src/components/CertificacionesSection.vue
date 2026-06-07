<template>
  <section id="certificaciones" class="relative py-24">
    <div class="max-w-5xl mx-auto px-6">
      <div class="mb-12">
        <p class="text-xs font-semibold uppercase tracking-[0.2em] text-neutral-500">Logros</p>
        <h2 class="text-3xl md:text-4xl font-bold text-neutral-900 mt-2">
          Certificaciones <span class="text-gradient">.</span>
        </h2>
        <div class="mt-4 h-px w-24 bg-gradient-to-r from-black/60 to-transparent"></div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <div v-for="cert in certificaciones" :key="cert.nombre"
          class="group relative flex items-center gap-5 glass rounded-2xl p-5 hover:border-black/30 transition-all duration-300 hover:-translate-y-0.5">
          <div class="relative flex-shrink-0">
            <div class="relative w-20 h-20 rounded-xl bg-white border border-black/10 flex items-center justify-center p-2">
              <img :src="cert.imagen" :alt="cert.nombre" class="w-full h-full object-contain" />
            </div>
          </div>
          <div class="flex-1 min-w-0">
            <p class="font-semibold text-neutral-900 truncate">{{ cert.nombre }}</p>
            <p class="text-sm text-neutral-500 mt-1">{{ cert.emisor }}</p>
            <span class="inline-flex items-center gap-1.5 mt-2 text-[11px] font-semibold uppercase tracking-wider text-amber-700 bg-amber-50 border border-amber-200 px-2 py-0.5 rounded-full">
              <span class="relative flex h-1.5 w-1.5">
                <span class="absolute inline-flex h-full w-full rounded-full bg-amber-400 opacity-75 animate-ping"></span>
                <span class="relative inline-flex rounded-full h-1.5 w-1.5 bg-amber-500"></span>
              </span>
              In progress
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const certificaciones = [
  {
    nombre: 'AWS Cloud Practitioner',
    emisor: 'Amazon Web Services',
    imagen: '/projects/aws-cloud-practitioner.png'
  }
]
</script>
