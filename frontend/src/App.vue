<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import ProyectosSection from './components/ProyectosSection.vue'
import ExperienciaSection from './components/ExperienciaSection.vue'
import CertificacionesSection from './components/CertificacionesSection.vue'
import EducacionSection from './components/EducacionSection.vue'
</script>

<template>
  <div class="min-h-screen bg-white text-neutral-900">
    <NavBar />

    <main>
      <HeroSection />
      <ProyectosSection />
      <ExperienciaSection />
      <CertificacionesSection />
      <EducacionSection />
    </main>

    <footer class="border-t border-black/10 py-8 text-center">
      <div class="max-w-4xl mx-auto px-6">
        <p class="text-sm text-neutral-500">
          © {{ new Date().getFullYear() }}
          <span class="text-neutral-900 font-medium">Pau García</span>
        </p>
      </div>
    </footer>
  </div>
</template>
