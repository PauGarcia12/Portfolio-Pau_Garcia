<template>
  <section id="proyectos" class="py-20 border-t border-black/5">
    <div class="max-w-5xl mx-auto px-6">
      <div class="mb-10">
        <p class="text-xs font-semibold uppercase tracking-[0.2em] text-neutral-500">Mi trabajo</p>
        <h2 class="text-3xl md:text-4xl font-bold text-neutral-900 mt-2">Proyectos</h2>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <article v-for="p in proyectos" :key="p.titulo"
          class="group card rounded-xl overflow-hidden hover:border-black/30 transition-colors">
          <div v-if="p.imagen" class="aspect-[16/10] bg-neutral-50 border-b border-black/5 overflow-hidden">
            <img :src="p.imagen" :alt="p.titulo" class="w-full h-full object-contain p-4" />
          </div>

          <div class="p-6">
            <h3 class="font-semibold text-lg text-neutral-900">{{ p.titulo }}</h3>
            <p class="text-sm text-neutral-600 mt-3 leading-relaxed">{{ p.descripcion }}</p>

            <div class="flex gap-2 mt-4 flex-wrap">
              <span v-for="tag in p.tags" :key="tag"
                class="bg-neutral-100 text-neutral-700 text-xs font-medium px-2.5 py-1 rounded-md border border-black/5">
                {{ tag }}
              </span>
            </div>

            <a v-if="p.link" :href="p.link" target="_blank"
              class="inline-flex items-center gap-1.5 mt-5 text-sm font-medium text-neutral-900 hover:text-neutral-600 transition-colors">
              Ver proyecto
              <svg xmlns="http://www.w3.org/2000/svg" class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                <path d="M5 12h14M13 5l7 7-7 7"/>
              </svg>
            </a>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const proyectos = [
  {
    titulo: 'Portfolio AWS',
    descripcion: 'Web estática desplegada con S3, CloudFront, ACM y Route 53. CI/CD con GitHub Actions.',
    tags: ['S3', 'CloudFront', 'Route 53', 'ACM', 'GitHub Actions'],
    link: 'https://github.com/PauGarcia77/Portfolio-aws',
    imagen: '/projects/portfolio-aws-architecture.png'
  },
  {
    titulo: 'App de Gastos',
    descripcion: 'SPA para el seguimiento de gastos personales. Sube extractos CSV, clasifica movimientos por categorías y visualiza KPIs y gráficos mensuales. Infraestructura serverless en AWS con Cognito, Lambda, API Gateway y S3',
    tags: ['Vue 3', 'AWS Cognito', 'Lambda', 'API Gateway', 'S3', 'CloudFront', 'GitHub Actions'],
    link: 'https://github.com/PauGarcia12/App-Gastos',
    imagen: '/projects/diagrama-app-gastos.jpg'
  }
]
</script>
