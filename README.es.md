# dabetai — Core API

<p align="center">
  <img src="https://img.shields.io/badge/NestJS-11.x-red?logo=nestjs&logoColor=white" alt="NestJS">
  <img src="https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Prisma-6.x-2D3748?logo=prisma" alt="Prisma">
  <img src="https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/JWT-Auth-000000?logo=jsonwebtokens&logoColor=white" alt="JWT">
</p>

<p align="center">
  <em>API REST del backend principal para la plataforma dabetai de monitoreo de diabetes, que conecta pacientes, médicos y modelos de inteligencia artificial.</em>
</p>

<p align="center">
  <a href="https://github.com/dabetai-org/api">Repositorio</a>
  ·
  <a href="https://github.com/dabetai-org/api/issues">Reportar Bug</a>
  ·
  <a href="https://chrisssp.vercel.app/assets/docs/papers/Prevenci%C3%B3n-de-Riesgos-de-la-Diabetes-Mediante-una-Plataforma-Inteligente-de-Monitorizaci%C3%B3n-y-Predicci%C3%B3n-de-Complicaciones-con-Inteligencia-Artificial.pdf">Artículo de Investigación</a>
</p>

<p align="center">
  <a href="README.md">🇬🇧 English</a> · <a href="README.es.md">🇪🇸 Español</a>
</p>

---

## Acerca de dabetai

**dabetai** es un ecosistema preventivo integral para la diabetes que predice complicaciones como retinopatía, nefropatía, neuropatía y pie diabético antes de que sean irreversibles.

Este repositorio contiene la **Core API** — el servicio backend central que:

- Gestiona autenticación y autorización con JWT y control de acceso por roles (paciente, médico, administrador)
- Administra registro de usuarios, perfiles y datos médicos
- Proporciona endpoints CRUD para pacientes y profesionales de la salud
- Se comunica con los modelos de IA para predecir complicaciones diabéticas
- Expone documentación autogenerada de la API mediante Swagger UI y Scalar

### Ecosistema

| Componente | Repositorio | Stack |
|-----------|-----------|-------|
| **App Móvil** | [dabetai-org/mobile-app](https://github.com/dabetai-org/mobile-app) | React Native 0.79, Expo 53, Tailwind CSS |
| **Portal Web** | [dabetai-org/web-app](https://github.com/dabetai-org/web-app) | Angular 19, Tailwind CSS |
| **Core API** (este) | [dabetai-org/api](https://github.com/dabetai-org/api) | NestJS 11, PostgreSQL, Prisma |
| **API de IA** | [dabetai-org/ai-api](https://github.com/dabetai-org/ai-api) | FastAPI, Python 3.11, MongoDB |
| **Modelos IA** | [dabetai-org/ai-models](https://github.com/dabetai-org/ai-models) | Python, scikit-learn, XGBoost, PyTorch |
| **Landing** | [dabetai-org/landing](https://github.com/dabetai-org/landing) | Astro, Tailwind CSS |

## Funcionalidades

- **Autenticación JWT** — Registro e inicio de sesión con roles (paciente, médico, administrador)
- **Gestión de Usuarios** — CRUD completo para pacientes y médicos
- **Datos Médicos** — Almacenamiento de información sobre diabetes y comorbilidades
- **Registro en 2 Pasos** — Cuenta básica + perfil médico
- **Documentación Automática** — Swagger UI y Scalar para probar las API
- **Seguridad** — Hash de contraseñas, validación de datos y tokens seguros
- **Base de Datos Relacional** — PostgreSQL con Prisma ORM
- **Estadísticas** — Endpoints para métricas de pacientes y médicos

## Inicio rápido

### Prerrequisitos

- Node.js 18+
- PostgreSQL 14+
- npm o yarn

### Instalación

```bash
git clone https://github.com/dabetai-org/api.git
cd api
npm install
```

Crea un archivo `.env`:

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

Iniciar servidor de desarrollo:

```bash
npm run start:dev
```

API disponible en `http://localhost:3000`

### Documentación de la API

- **Swagger UI**: `http://localhost:3000/api/docs`
- **Scalar UI**: `http://localhost:3000/api/scalar`

## Arquitectura

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

## Contribuciones

Por favor lee [CONTRIBUTING.md](CONTRIBUTING.md) para nuestras convenciones de ramas, commits y flujo de PRs.

## Licencia

Este proyecto está licenciado bajo GNU General Public License v3.0 — consulta el archivo [LICENSE](LICENSE) para más detalles.

## Reconocimientos

**Autores:**
- Cardenas Cabal Fermín
- Ortiz Pérez Alejandro — alex03ortizperez@gmail.com
- Serrano Puertos Jorge Christian — christian.serrano.puertos@gmail.com

**Asesores:**
- Guarneros Nolasco Luis Rolando
- Cruz Ramos Nancy Aracely

**Apoyo Académico:**
- Universidad Tecnológica del Centro de Veracruz
