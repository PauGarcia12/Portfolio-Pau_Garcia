<template>
  <section id="hero" class="py-20 md:py-28">
    <div class="max-w-5xl mx-auto px-6">
      <div class="flex flex-col md:flex-row items-center gap-10">
        <div class="flex-shrink-0">
          <div class="w-28 h-28 md:w-32 md:h-32 rounded-full overflow-hidden border border-black/10 bg-neutral-100">
            <img src="/pau.jpg" alt="Pau García" class="w-full h-full object-cover" />
          </div>
        </div>

        <div class="text-center md:text-left">
          <h1 class="text-4xl md:text-5xl font-bold tracking-tight text-neutral-900">
            Hola, soy Pau García
          </h1>
          <p class="text-neutral-600 mt-3 text-lg font-medium">
            Cloud Engineer · DevSecOps · AWS
          </p>
          <p class="text-neutral-600 mt-4 max-w-xl text-sm md:text-base leading-relaxed">
            Apasionado del desarrollo de software, terminando mi FP Superior en DAM y adentrándome en el mundo cloud.
            Aprendiendo AWS, DevOps y todo lo que rodea a la ingeniería en la nube con ganas de crecer y construir cosas que escalen.
          </p>
          <div class="flex gap-2 mt-5 flex-wrap justify-center md:justify-start">
            <span v-for="tag in tags" :key="tag"
              class="bg-neutral-100 text-neutral-700 text-xs font-medium px-3 py-1 rounded-full border border-black/5">
              {{ tag }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const tags = ['AWS Cloud', 'DevSecOps', 'Vue.js', 'CI/CD']
</script>
