# Dabetai API — <span id="en2">EN</span> · <a href="#es_api">ES</a>

RESTful backend API for the Dabetai diabetes monitoring platform, connecting patients, healthcare professionals, and AI prediction models.

<p align="center">
  <img src="https://img.shields.io/badge/NestJS-11.x-red?logo=nestjs" alt="NestJS">
  <img src="https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript" alt="TypeScript">
  <img src="https://img.shields.io/badge/Prisma-6.x-2D3748?logo=prisma" alt="Prisma">
  <img src="https://img.shields.io/badge/PostgreSQL-16-blue?logo=postgresql" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/JWT-Auth-green?logo=jsonwebtokens" alt="JWT">
</p>

## API Documentation

Interactive API docs available via Swagger UI and Scalar:

- **Swagger UI**: `http://localhost:3000/api/docs`
- **Scalar UI**: `http://localhost:3000/api/scalar`

<p align="center">
  <img src="./assets/swagger-preview.png" alt="Swagger UI" width="400"/>
  <img src="./assets/scalar-preview.png" alt="Scalar UI" width="400"/>
</p>

## What is Dabetai API?

**Dabetai API** is the central backend of the Dabetai platform. It handles authentication, user management (patients and healthcare professionals), medical data storage, and communication with AI models for predicting diabetic complications (retinopathy, nephropathy, neuropathy, and diabetic foot).

---

## Features

- **JWT authentication** — Registration and login with role-based access (patient, doctor, admin)
- **User management** — Full CRUD for patients and healthcare professionals
- **Medical data** — Storage for diabetes and comorbidity information
- **2-step registration** — Basic account + medical profile completion
- **Auto-generated docs** — Swagger UI and Scalar for API testing
- **Security** — Password hashing, data validation, secure tokens
- **Relational database** — PostgreSQL with Prisma ORM
- **Statistics** — Endpoints for patient and doctor metrics

---

## Tech Stack

- **NestJS** — Scalable, modular backend framework
- **TypeScript** — Static typing for robustness
- **Prisma ORM** — Type-safe database management
- **PostgreSQL** — Relational database
- **JWT** — Secure token-based authentication
- **Swagger/OpenAPI** — Automatic API documentation
- **bcrypt** — Secure password hashing
- **class-validator** — Input validation

---

## Quick Start

### Prerequisites

- Node.js (v18+)
- PostgreSQL (v14+)
- npm or yarn

### Steps

```bash
git clone https://github.com/dabetai-org/api.git
cd api
npm install
```

Create `.env`:

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

Start server:

```bash
npm run start:dev
```

API available at `http://localhost:3000`

---

## Ecosystem

| Repository | Purpose | Status |
|---|---|---|
| [mobile-app](https://github.com/dabetai-org/mobile-app) | Patient mobile app | Active |
| [web-app](https://github.com/dabetai-org/web-app) | Doctor web app | Active |
| [api](https://github.com/dabetai-org/api) | Main backend API | Active |
| [ai-api](https://github.com/dabetai-org/ai-api) | AI prediction API | Active |
| [ai-models](https://github.com/dabetai-org/ai-models) | ML models | Active |
| [landing](https://github.com/dabetai-org/landing) | Landing page | Active |

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Acknowledgments

Developed by:

- Cardenas Cabal Fermín
- Ortiz Pérez Alejandro
- Serrano Puertos Jorge Christian

Advisors:

- Guarneros Nolasco Luis Rolando
- Cruz Ramos Nancy Aracely

Academic support:

- Universidad Tecnológica del Centro de Veracruz
