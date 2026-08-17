<template>
  <section id="certificaciones" class="py-20 border-t border-black/5">
    <div class="max-w-5xl mx-auto px-6">
      <div class="mb-10">
        <p class="text-xs font-semibold uppercase tracking-[0.2em] text-neutral-500">Logros</p>
        <h2 class="text-3xl md:text-4xl font-bold text-neutral-900 mt-2">Certificaciones</h2>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <div v-for="cert in certificaciones" :key="cert.nombre"
          class="flex items-center gap-5 card rounded-xl p-5 hover:border-black/30 transition-colors">
          <div class="flex-shrink-0 w-20 h-20 rounded-lg bg-white border border-black/10 flex items-center justify-center p-2">
            <img :src="cert.imagen" :alt="cert.nombre" class="w-full h-full object-contain" />
          </div>
          <div class="flex-1 min-w-0">
            <p class="font-semibold text-neutral-900 truncate">{{ cert.nombre }}</p>
            <p class="text-sm text-neutral-500 mt-1">{{ cert.emisor }}</p>
            <span class="inline-flex items-center gap-1.5 mt-2 text-[11px] font-semibold uppercase tracking-wider text-amber-700 bg-amber-50 border border-amber-200 px-2 py-0.5 rounded-full">
              <span class="w-1.5 h-1.5 rounded-full bg-amber-500"></span>
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
    nombre: 'AWS Solutions Architect Associate',
    emisor: 'Amazon Web Services',
    imagen: '/projects/aws-solutions-architect-associate.png'
  }
]
</script>
