# Portfolio Personal — Pau García

> Portfolio estático desplegado en AWS con CI/CD automatizado. Desarrollado con Vue 3 y Tailwind CSS.

---

## Stack e Infraestructura

| Servicio | Uso |
|---|---|
| **AWS S3** | Almacenamiento de archivos estáticos y hosting web |
| **AWS CloudFront** | CDN — distribución global de contenido y caché |
| **AWS ACM** | Certificado SSL/TLS (HTTPS) |
| **AWS Route 53** | Gestión del DNS y dominio personalizado |
| **GitHub Actions** | CI/CD — deploy automático en cada push a `main` |
| **Vue 3 + Vite** | Framework frontend |
| **Tailwind CSS** | Estilos |

---

## Arquitectura

```
Usuario
 │
 ▼
Route 53 (resolución DNS)
 │
 ▼
CloudFront (CDN + HTTPS via ACM)
 │
 ▼
S3 Bucket (contenido estático)
```

---

## Pipeline CI/CD

Cada push a `main` lanza automáticamente un workflow de GitHub Actions, sin ninguna intervención manual.

```
Push a main
     │
     ▼
GitHub Actions
     ├── Build de la app Vue (npm run build)
     ├── Sync /dist → bucket S3
     └── Invalidación de caché en CloudFront
```

Las credenciales de AWS y los nombres de los buckets se almacenan como **GitHub Secrets** — nunca hardcodeados en el repositorio.

---

## Estructura del proyecto

```
portfolio/
├── src/
│   ├── components/
│   │   ├── HeroSection.vue
│   │   ├── ProyectosSection.vue
│   │   ├── CertificacionesSection.vue
│   │   ├── EducacionSection.vue
│   │   └── ContactoSection.vue
│   └── App.vue
├── public/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── vite.config.js
└── tailwind.config.js
```

---

## Deploy manual

Si quieres desplegar manualmente sin el pipeline de CI/CD:

```bash
# Build del proyecto
npm run build

# Sync a S3
aws s3 sync ./dist s3://TU-BUCKET --delete

# Invalidar caché de CloudFront
aws cloudfront create-invalidation \
  --distribution-id TU-DISTRIBUTION-ID \
  --paths "/*"
```

---

## Sobre este proyecto

Portfolio personal desarrollado tras finalizar el **Grado Superior en Desarrollo de Aplicaciones Multiplataforma (DAM)**. Mi primer paso práctico en infraestructura cloud real.

El objetivo era ir más allá de simplemente alojar una web y aprender cómo funcionan de verdad los despliegues en AWS a nivel de producción: dominios personalizados, certificados HTTPS, caché en CDN y pipelines totalmente automatizados.

Actualmente en búsqueda de mi primera oportunidad laboral en el área de **Cloud Engineering / DevOps**, y preparando la certificación **AWS Solutions Architect Associate**.