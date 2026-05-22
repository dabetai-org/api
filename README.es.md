<a href="#en2"><span id="es_api">ES</span></a> · <a href="#en2">EN</a>

# Dabetai API

API REST del backend principal para la plataforma Dabetai de monitoreo de diabetes, que conecta pacientes, médicos y modelos de inteligencia artificial.

<p align="center">
  <img src="https://img.shields.io/badge/NestJS-11.x-red?logo=nestjs" alt="NestJS">
  <img src="https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript" alt="TypeScript">
  <img src="https://img.shields.io/badge/Prisma-6.x-2D3748?logo=prisma" alt="Prisma">
  <img src="https://img.shields.io/badge/PostgreSQL-16-blue?logo=postgresql" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/JWT-Auth-green?logo=jsonwebtokens" alt="JWT">
</p>

## Documentación de la API

Documentación interactiva disponible a través de Swagger UI y Scalar:

- **Swagger UI**: `http://localhost:3000/api/docs`
- **Scalar UI**: `http://localhost:3000/api/scalar`

<p align="center">
  <img src="./assets/swagger-preview.png" alt="Swagger UI" width="400"/>
  <img src="./assets/scalar-preview.png" alt="Scalar UI" width="400"/>
</p>

## ¿Qué es Dabetai API?

**Dabetai API** es el backend central de la plataforma Dabetai. Gestiona la autenticación, el registro de usuarios (pacientes y médicos), el almacenamiento de datos médicos y la comunicación con los modelos de IA para predecir complicaciones diabéticas (retinopatía, nefropatía, neuropatía y pie diabético).

---

## Funcionalidades

- **Autenticación JWT** — Registro e inicio de sesión con roles (paciente, médico, administrador)
- **Gestión de usuarios** — CRUD completo para pacientes y médicos
- **Datos médicos** — Almacenamiento de información sobre diabetes y comorbilidades
- **Registro en 2 pasos** — Cuenta básica + perfil médico
- **Documentación automática** — Swagger UI y Scalar para probar las API
- **Seguridad** — Hash de contraseñas, validación de datos y tokens seguros
- **Base de datos relacional** — PostgreSQL con Prisma ORM
- **Estadísticas** — Endpoints para métricas de pacientes y médicos

---

## Tecnologías

- **NestJS** — Framework backend escalable y modular
- **TypeScript** — Tipado estático para mayor robustez
- **Prisma ORM** — Gestión type-safe de base de datos
- **PostgreSQL** — Base de datos relacional
- **JWT** — Autenticación por tokens seguros
- **Swagger/OpenAPI** — Documentación automática de API
- **bcrypt** — Hash seguro de contraseñas
- **class-validator** — Validación de datos de entrada

---

## Inicio rápido

### Prerrequisitos

- Node.js (v18+)
- PostgreSQL (v14+)
- npm o yarn

### Pasos

```bash
git clone https://github.com/dabetai-org/api.git
cd api
npm install
```

Crear `.env`:

```env
DATABASE_URL="postgresql://usuario:contraseña@localhost:5432/dabetai_db"
JWT_SECRET="tu_jwt_secret_seguro"
NODE_ENV="development"
```

Ejecutar migraciones:

```bash
npx prisma migrate dev
npx prisma generate
```

Iniciar servidor:

```bash
npm run start:dev
```

API disponible en `http://localhost:3000`

---

## Ecosistema

| Repositorio | Propósito | Estado |
|---|---|---|
| [mobile-app](https://github.com/dabetai-org/mobile-app) | App para pacientes | Activo |
| [web-app](https://github.com/dabetai-org/web-app) | App web para médicos | Activo |
| [api](https://github.com/dabetai-org/api) | API principal del backend | Activo |
| [ai-api](https://github.com/dabetai-org/ai-api) | API de IA y predicciones | Activo |
| [ai-models](https://github.com/dabetai-org/ai-models) | Modelos de machine learning | Activo |
| [landing](https://github.com/dabetai-org/landing) | Página de aterrizaje | Activo |

---

## Contribuciones

Ver [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Reconocimientos

Desarrollado por:

- Cardenas Cabal Fermín
- Ortiz Pérez Alejandro
- Serrano Puertos Jorge Christian

Asesores:

- Guarneros Nolasco Luis Rolando
- Cruz Ramos Nancy Aracely

Apoyo académico:

- Universidad Tecnológica del Centro de Veracruz
