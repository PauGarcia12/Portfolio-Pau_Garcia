<template>
  <nav class="sticky top-0 z-50 bg-white/90 backdrop-blur border-b border-black/10">
    <div class="max-w-5xl mx-auto px-6 h-16 flex items-center justify-between gap-6">
      <a href="#hero" class="flex items-center gap-2.5">
        <span class="inline-block h-9 w-9 rounded-full overflow-hidden border border-black/10 bg-neutral-100">
          <img src="/pau.jpg" alt="Pau García" class="w-full h-full object-cover object-top" />
        </span>
        <span class="font-semibold tracking-tight text-neutral-900">Pau Garcia</span>
      </a>

      <div class="hidden md:flex gap-1">
        <a v-for="link in links" :key="link.label" :href="link.href"
          class="text-sm text-neutral-600 hover:text-neutral-900 px-3 py-2 rounded-md transition-colors">
          {{ link.label }}
        </a>
      </div>

      <div class="flex items-center gap-1.5">
        <a href="mailto:paugarciaparets@gmail.com" aria-label="Email"
          class="inline-flex items-center justify-center w-9 h-9 rounded-md text-neutral-600 hover:text-neutral-900 hover:bg-neutral-100 transition-colors">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-[18px] h-[18px]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
            <polyline points="22,6 12,13 2,6"/>
          </svg>
        </a>
        <a href="https://www.linkedin.com/in/pau-garcia-parets-9a55a237b" target="_blank" rel="noopener" aria-label="LinkedIn"
          class="inline-flex items-center justify-center w-9 h-9 rounded-md text-neutral-600 hover:text-neutral-900 hover:bg-neutral-100 transition-colors">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-[18px] h-[18px]" viewBox="0 0 24 24" fill="currentColor">
            <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
          </svg>
        </a>
        <a href="https://github.com/PauGarcia12" target="_blank" rel="noopener" aria-label="GitHub"
          class="inline-flex items-center justify-center w-9 h-9 rounded-md text-neutral-600 hover:text-neutral-900 hover:bg-neutral-100 transition-colors">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-[18px] h-[18px]" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
          </svg>
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
