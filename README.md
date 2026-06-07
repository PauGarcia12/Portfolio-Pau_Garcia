# 🌐 Portfolio Personal

> Web estática desplegada con S3, CloudFront, ACM y Route 53. CI/CD con GitHub Actions.

---

## 🚀 Stack & Infraestructura

| Servicio | Uso |
|---|---|
| **AWS S3** | Almacenamiento y hosting de la web estática |
| **AWS CloudFront** | CDN y distribución global del contenido |
| **AWS ACM** | Certificado SSL/TLS (HTTPS) |
| **AWS Route 53** | Gestión del dominio y DNS |
| **GitHub Actions** | CI/CD — deploy automático en cada push |

---

## 🏗️ Arquitectura

```
Usuario
   │
   ▼
Route 53 (DNS)
   │
   ▼
CloudFront (CDN + HTTPS via ACM)
   │
   ▼
S3 Bucket (contenido estático)
```

---

## ⚙️ CI/CD

Cada push a `main` lanza automáticamente un workflow de GitHub Actions que sincroniza los archivos con el bucket de S3 e invalida la caché de CloudFront.

```yaml
# .github/workflows/deploy.yml
- Sync a S3
- Invalidate CloudFront distribution
```

---

## 📁 Estructura del proyecto

```
portfolio/
├── index.html
├── assets/
│   ├── css/
│   ├── js/
│   └── img/
└── .github/
    └── workflows/
        └── deploy.yml
```

---

## 🛠️ Deploy manual

Si quieres desplegar manualmente:

```bash
# Subir archivos a S3
aws s3 sync . s3://TU-BUCKET --delete

# Invalidar caché de CloudFront
aws cloudfront create-invalidation \
  --distribution-id TU-DISTRIBUTION-ID \
  --paths "/*"
```

---

## 📌 Sobre este proyecto

Portfolio personal desarrollado mientras finalizo el **Grado Superior en DAM**, con el que empiezo a explorar el ecosistema **AWS, DevOps y Cloud Engineering**. Este proyecto es mi primer paso práctico en infraestructura cloud real.


