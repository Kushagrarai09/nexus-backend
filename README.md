# Nexus Backend

Nexus is an expandable commerce and order-management backend built with TypeScript, Node.js and Express. It is designed as a hands-on backend engineering curriculum: start with a modular monolith, then evolve toward event-driven services and distributed infrastructure.

## Included now

- TypeScript + Express REST API
- PostgreSQL + Prisma data model
- Registration, login, access JWT and rotating refresh token
- Role-based authorization middleware
- Product listing, search, pagination and seller product creation
- Transactional order creation with stock decrement and idempotency key
- Educational mock payment confirmation
- Optional Redis cache with graceful cache fallback
- RabbitMQ notification worker skeleton
- Helmet, CORS, rate limiting, Zod validation
- Pino logging and Prometheus metrics
- Swagger UI shell
- Docker Compose for PostgreSQL, Redis and RabbitMQ
- Vitest + Supertest starter tests
- GitHub Actions CI starter
- Architecture, security, API and roadmap documentation

## Requirements

- Node.js 20+
- npm
- Docker Desktop (recommended)
- Git

## Setup on Windows PowerShell

1. Copy `.env.example` to `.env`.
2. Replace both JWT secrets with long random values.
3. Start dependencies: `docker compose up -d`.
4. Install dependencies: `npm install`.
5. Generate Prisma client: `npm run db:generate`.
6. Create and apply the first migration: `npm run db:migrate` (name it `init`).
7. Seed demo data: `npm run db:seed`.
8. Start API: `npm run dev`.

API: http://localhost:3000  
Health: http://localhost:3000/health  
Metrics: http://localhost:3000/metrics  
API docs: http://localhost:3000/docs  
RabbitMQ management: http://localhost:15672 (nexus / nexus_dev_password)

## Useful commands

```powershell
npm run typecheck
npm test
npm run build
npm start
npm run worker
```

## Demo seller

After seeding:
- Email: `seller@nexus.local`
- Password: `ChangeMe123!`

Change this immediately in any shared environment. The seed account is for local development only.

## Important limitations

This is a runnable learning foundation, not a finished production commerce system. Payment confirmation is mocked. The RabbitMQ worker is a demonstration consumer and is not yet connected to a transactional outbox publisher. Kafka, Elasticsearch, WebSockets, SSE, Kubernetes, Nginx deployment, distributed tracing, full refund workflows, production OAuth/OIDC and service extraction are documented future milestones rather than falsely claimed as complete.
