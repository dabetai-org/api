# dabetai — Core API

<p align="center">
  <img src="https://img.shields.io/badge/NestJS-11.x-red?logo=nestjs&logoColor=white" alt="NestJS">
  <img src="https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Prisma-6.x-2D3748?logo=prisma" alt="Prisma">
  <img src="https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/JWT-Auth-000000?logo=jsonwebtokens&logoColor=white" alt="JWT">
</p>

<p align="center">
  <em>RESTful backend API for the dabetai diabetes monitoring platform, connecting patients, healthcare professionals, and AI prediction models.</em>
</p>

<p align="center">
  <a href="https://github.com/dabetai-org/api">Repository</a>
  ·
  <a href="https://github.com/dabetai-org/api/issues">Report Bug</a>
  ·
  <a href="https://chrisssp.vercel.app/assets/docs/papers/Prevenci%C3%B3n-de-Riesgos-de-la-Diabetes-Mediante-una-Plataforma-Inteligente-de-Monitorizaci%C3%B3n-y-Predicci%C3%B3n-de-Complicaciones-con-Inteligencia-Artificial.pdf">Research Paper</a>
</p>

<p align="center">
  <a href="README.md">🇬🇧 English</a> · <a href="README.es.md">🇪🇸 Español</a>
</p>

---

## About dabetai

**dabetai** is a comprehensive preventive ecosystem for diabetes that predicts complications like retinopathy, nephropathy, neuropathy, and diabetic foot before they become irreversible.

This repository contains the **Core API** — the central backend service that:

- Handles authentication and authorization with JWT and role-based access (patient, doctor, admin)
- Manages user registration, profiles, and medical data
- Provides CRUD endpoints for patients and healthcare professionals
- Communicates with AI models for predicting diabetic complications
- Exposes auto-generated API documentation via Swagger UI and Scalar

### Ecosystem

| Component | Repository | Stack |
|-----------|-----------|-------|
| **Mobile App** | [dabetai-org/mobile-app](https://github.com/dabetai-org/mobile-app) | React Native 0.79, Expo 53, Tailwind CSS |
| **Web Portal** | [dabetai-org/web-app](https://github.com/dabetai-org/web-app) | Angular 19, Tailwind CSS |
| **Core API** (this) | [dabetai-org/api](https://github.com/dabetai-org/api) | NestJS 11, PostgreSQL, Prisma |
| **AI Inference API** | [dabetai-org/ai-api](https://github.com/dabetai-org/ai-api) | FastAPI, Python 3.11, MongoDB |
| **AI Models** | [dabetai-org/ai-models](https://github.com/dabetai-org/ai-models) | Python, scikit-learn, XGBoost, PyTorch |
| **Landing** | [dabetai-org/landing](https://github.com/dabetai-org/landing) | Astro, Tailwind CSS |

## Features

- **JWT Authentication** — Registration and login with role-based access (patient, doctor, admin)
- **User Management** — Full CRUD for patients and healthcare professionals
- **Medical Data** — Storage for diabetes and comorbidity information
- **2-Step Registration** — Basic account + medical profile completion
- **Auto-Generated Docs** — Swagger UI and Scalar for API testing
- **Security** — Password hashing, data validation, secure tokens
- **Relational Database** — PostgreSQL with Prisma ORM
- **Statistics** — Endpoints for patient and doctor metrics

## Quick Start

### Prerequisites

- Node.js 18+
- PostgreSQL 14+
- npm or yarn

### Setup

```bash
git clone https://github.com/dabetai-org/api.git
cd api
npm install
```

Create a `.env` file:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/dabetai_db"
JWT_SECRET="your_secure_jwt_secret"
NODE_ENV="development"
```

Run migrations:

```bash
npx prisma migrate dev
npx prisma generate
```

Start the development server:

```bash
npm run start:dev
```

API available at `http://localhost:3000`

### API Documentation

- **Swagger UI**: `http://localhost:3000/api/docs`
- **Scalar UI**: `http://localhost:3000/api/scalar`

## Architecture

```
┌─────────────────────────────────────────┐
│              Core API (NestJS)                 │
│  ┌──────────┐ ┌──────────┐ ┌────────────────┐  │
│  │   Auth   │ │  Users   │ │  Medical     │  │
│  │  Module  │ │  Module  │ │  Data Module │  │
│  └────┤─────┘ └────┤─────┘ └──────┤──────────┘  │
│       │            │              │           │
│  ┌────├────────────├──────────────────├───────────┐   │
│  │           Prisma ORM Layer             │   │
│  └──────────────────────────┘   │
└──────────────────├─────────────────────────┘
                    │
             ┌──────├──────┐
             │  PostgreSQL │
             └─────────────┘
```

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for branch naming, commit conventions, and PR workflow.

## License

This project is licensed under the GNU General Public License v3.0 — see the [LICENSE](LICENSE) file for details.

## Acknowledgments

**Authors:**
- Cardenas Cabal Fermín
- Ortiz Pérez Alejandro — alex03ortizperez@gmail.com
- Serrano Puertos Jorge Christian — christian.serrano.puertos@gmail.com

**Advisors:**
- Guarneros Nolasco Luis Rolando
- Cruz Ramos Nancy Aracely

**Academic Support:**
- Universidad Tecnológica del Centro de Veracruz
