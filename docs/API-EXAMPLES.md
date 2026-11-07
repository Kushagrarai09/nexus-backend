# API Examples

Base URL: `http://localhost:3000`

## Health

```http
GET /health
```

## Authentication

```http
POST /api/v1/auth/register
Content-Type: application/json

{"name":"Demo Customer","email":"customer@example.com","password":"Use-a-long-unique-password"}
```

```http
POST /api/v1/auth/login
Content-Type: application/json

{"email":"customer@example.com","password":"Use-a-long-unique-password"}
```

Use the returned access token as `Authorization: Bearer <token>` for protected requests.

## Products

```http
GET /api/v1/products?page=1&limit=20&search=laptop
```

## Orders

```http
POST /api/v1/orders
Authorization: Bearer <token>
Idempotency-Key: order-demo-001
Content-Type: application/json

{"items":[{"productId":"PRODUCT_ID","quantity":1}]}
```

Check the actual mounted routes and Zod schemas in `src/modules/` before relying on any sample request; API contracts may change as the learning project evolves.
