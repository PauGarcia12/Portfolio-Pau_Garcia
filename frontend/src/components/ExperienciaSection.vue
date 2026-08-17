<template>
  <section id="experiencia" class="py-20 border-t border-black/5">
    <div class="max-w-5xl mx-auto px-6">
      <div class="mb-10">
        <p class="text-xs font-semibold uppercase tracking-[0.2em] text-neutral-500">Trayectoria</p>
        <h2 class="text-3xl md:text-4xl font-bold text-neutral-900 mt-2">Experiencia laboral</h2>
      </div>

      <div class="flex flex-col gap-6">
        <div v-for="empresa in experiencia" :key="empresa.nombre" class="card rounded-xl p-6">
          <div class="flex items-start justify-between gap-4 flex-wrap">
            <div>
              <h3 class="font-semibold text-lg text-neutral-900">{{ empresa.nombre }}</h3>
              <p class="text-sm text-neutral-500 mt-1">{{ empresa.duracion }} · {{ empresa.modalidad }}</p>
            </div>
          </div>

          <div class="relative mt-6 pl-6 border-l border-black/10 flex flex-col gap-6">
            <div v-for="rol in empresa.roles" :key="rol.titulo" class="relative">
              <span class="absolute -left-[27px] top-1.5 w-2.5 h-2.5 rounded-full bg-black ring-4 ring-white"></span>

              <div class="flex justify-between items-start gap-4 flex-wrap">
                <div>
                  <h4 class="font-semibold text-neutral-900">{{ rol.titulo }}</h4>
                  <p class="text-sm text-neutral-600 mt-0.5">{{ rol.contrato }}</p>
                  <p class="text-xs text-neutral-500 mt-1">{{ rol.periodo }} · {{ rol.ubicacion }}</p>
                </div>
              </div>

              <p class="text-sm text-neutral-600 mt-3 leading-relaxed">{{ rol.descripcion }}</p>

              <div class="flex gap-2 mt-3 flex-wrap">
                <span v-for="tag in rol.tags" :key="tag"
                  class="bg-neutral-100 text-neutral-700 text-xs font-medium px-2.5 py-1 rounded-md border border-black/5">
                  {{ tag }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const experiencia = [
  {
    nombre: 'Farmadosis',
    duracion: '1 año 5 meses',
    modalidad: 'Presencial',
    roles: [
      {
        titulo: 'Junior Software Developer',
        contrato: 'Jornada completa',
        periodo: 'jun. 2026 - actualidad',
        ubicacion: 'Palma',
        descripcion: 'Desarrollo y mantenimiento de aplicaciones con PHP y MySQL, gestión y configuración de servidores Linux, y creación de pequeños programas en C# para automatizar tareas y dar soporte al equipo.',
        tags: ['PHP', 'MySQL', 'Linux', 'C#']
      },
      {
        titulo: 'Junior Software Developer',
        contrato: 'Contrato de formación',
        periodo: 'abr. 2025 - jun. 2026 · 1 año 3 meses',
        ubicacion: 'Palma, Islas Baleares, España',
        descripcion: 'Principalmente me enfoqué en el desarrollo y mantenimiento de aplicaciones internas utilizando PHP y bases de datos MySQL, contribuyendo tanto al diseño como a la optimización de consultas. Trabajé también en tareas de soporte y mejora continua junto al equipo.',
        tags: ['PHP', 'MySQL', 'Linux', 'Git']
      }
    ]
  }
]
</script>
