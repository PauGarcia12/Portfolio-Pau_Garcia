# Personal Portfolio — Pau García

> Static portfolio deployed on AWS with automated CI/CD. Built with Vue 3 and Tailwind CSS.

---

## Stack & Infrastructure

| Service | Purpose |
|---|---|
| **AWS S3** | Static file storage and website hosting |
| **AWS CloudFront** | CDN — global content distribution and caching |
| **AWS ACM** | SSL/TLS certificate (HTTPS) |
| **AWS Route 53** | DNS management and custom domain |
| **GitHub Actions** | CI/CD — automated deploy on every push to `main` |
| **Vue 3 + Vite** | Frontend framework |
| **Tailwind CSS** | Styling |

---

## Architecture

```
User
 │
 ▼
Route 53 (DNS resolution)
 │
 ▼
CloudFront (CDN + HTTPS via ACM)
 │
 ▼
S3 Bucket (static content)
```

---

## CI/CD Pipeline

Every push to `main` automatically triggers a GitHub Actions workflow, no manual intervention needed.

```
Push to main
     │
     ▼
GitHub Actions
     ├── Build Vue app (npm run build)
     ├── Sync /dist → S3 bucket
     └── Invalidate CloudFront cache
```

Secrets like AWS credentials and bucket names are stored as **GitHub Secrets** — never hardcoded in the repository.

---

## Project Structure

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

## Manual Deploy

If you want to deploy manually without the CI/CD pipeline:

```bash
# Build the project
npm run build

# Sync to S3
aws s3 sync ./dist s3://YOUR-BUCKET-NAME --delete

# Invalidate CloudFront cache
aws cloudfront create-invalidation \
  --distribution-id YOUR-DISTRIBUTION-ID \
  --paths "/*"
```

---

## About

Personal portfolio built while finishing my **Higher Degree in Multiplatform Application Development (DAM)** — my first hands-on step into real cloud infrastructure.

The goal was to go beyond just hosting a website and learn how production-grade AWS deployments actually work: custom domains, HTTPS certificates, CDN caching, and fully automated pipelines.

Currently preparing for the **AWS Solutions Architect Associate** certification.
