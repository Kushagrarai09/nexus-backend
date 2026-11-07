# Nexus Architecture

## Current architecture: modular monolith

The initial deployable unit is one Express application. Business capabilities are separated into modules:
- Auth
- Products
- Orders
- Payments
- Health

The application uses PostgreSQL as the source of truth. Redis is an optional cache and RabbitMQ is an optional asynchronous messaging broker.

## Request lifecycle

Client -> HTTP middleware -> route -> validation -> authentication/authorization -> business logic -> Prisma -> PostgreSQL -> response.

## Evolution plan

Keep the modular monolith until boundaries, data ownership, operational requirements and deployment needs justify extraction. Add an outbox publisher, idempotent consumers, retries and dead-letter handling before relying on asynchronous events. Distributed services introduce network failure and eventual consistency; they are not a default optimization.

## Failure boundaries

- PostgreSQL is required for durable commerce state.
- Redis failures should degrade cache functionality, not corrupt source data.
- RabbitMQ messages need acknowledgements, retry policy and dead-letter routing.
- Payment integrations must verify provider signatures and be idempotent; the current payment flow is an educational mock.
