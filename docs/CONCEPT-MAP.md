# Backend Concept Map

| Concept | Project area |
|---|---|
| HTTP / REST | `src/app.ts`, `src/modules/` |
| TypeScript / Node.js | `src/`, `tsconfig.json`, `package.json` |
| Configuration | `src/config/env.ts`, `.env.example` |
| Middleware | `src/middleware/` |
| Relational data modeling | `prisma/schema.prisma` |
| SQL / ORM / migrations | Prisma schema and npm scripts |
| Authentication | `src/modules/auth/`, token helpers |
| Authorization | role middleware and route policies |
| Validation | Zod schemas and validation middleware |
| Transactions | order creation workflow |
| Idempotency | order/payment command handling |
| Caching | `src/lib/redis.ts` |
| Messaging | `src/workers/notification.worker.ts` |
| Observability | `src/observability/`, logger |
| Testing | `tests/`, Vitest, Supertest |
| CI | `.github/workflows/ci.yml` |
| Containers | `Dockerfile`, `docker-compose.yml` |
| Distributed systems | outbox, retries, sagas and extraction (learning milestones) |
