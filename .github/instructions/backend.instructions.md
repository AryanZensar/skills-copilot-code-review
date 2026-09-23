---
applyTo: "src/**/*.py,**/backend/**/*.py"
---

## Backend Review Guidelines

- Define API endpoints in `src/backend/routers/` and keep database access in `src/backend/database.py` unless the existing boundary requires otherwise.
- Validate request input at the API boundary, including email format, identifiers, allowed values, and authorization requirements.
- Ensure authentication and authorization checks cannot be bypassed by caller-controlled fields or client-side state.
- Use safe, atomic database operations for capacity and registration constraints; do not rely on a separate read followed by a write when concurrent requests matter.
- Do not expose passwords, secrets, or unnecessary personal data in responses or logs. Use environment configuration for deployment-specific values.
- Keep API documentation and frontend callers synchronized, and flag breaking contract changes explicitly.
- Return deliberate HTTP errors and preserve useful server-side diagnostics without leaking implementation details to clients.