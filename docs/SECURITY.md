# Security Notes

This project is a learning foundation and is not security-certified.

- Never commit `.env`, real credentials, private keys or production data.
- Replace development secrets with strong, unique random values.
- Hash passwords using a modern password-hashing function; never store plaintext.
- Validate and bound all client input.
- Enforce authorization for each protected resource and action.
- Add rate limits, secure headers, strict CORS, request-size limits and audit events.
- Avoid logging passwords, tokens, payment data or other secrets.
- Use transactions and idempotency for inventory and order operations.
- Verify payment webhook signatures and protect against replay before integrating a real provider.
- Configure TLS, backups, monitoring, least-privilege database access and dependency scanning before deployment.
- Demo seller credentials exist only for local development; change them immediately in shared environments.
