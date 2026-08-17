<template>
  <nav class="sticky top-0 z-50 bg-white/90 backdrop-blur border-b border-black/10">
    <div class="max-w-5xl mx-auto px-6 h-16 flex items-center justify-between">
      <a href="#hero" class="flex items-center gap-2.5">
        <span class="inline-block h-8 w-8 rounded-full overflow-hidden border border-black/10 bg-neutral-100">
          <img src="/pau.jpg" alt="Pau García" class="w-full h-full object-cover" />
        </span>
        <span class="font-semibold tracking-tight text-neutral-900">Pau Garcia</span>
      </a>
      <div class="hidden md:flex gap-1">
        <a v-for="link in links" :key="link.label" :href="link.href"
          class="text-sm text-neutral-600 hover:text-neutral-900 px-3 py-2 rounded-md transition-colors">
          {{ link.label }}
        </a>
      </div>
    </div>
  </nav>
</template>

<script setup>
const links = [
  { label: 'Sobre mí',        href: '#hero' },
  { label: 'Proyectos',       href: '#proyectos' },
  { label: 'Experiencia',     href: '#experiencia' },
  { label: 'Certificaciones', href: '#certificaciones' },
  { label: 'Educación',       href: '#educacion' },
]
</script>
