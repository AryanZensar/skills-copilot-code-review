## Project Context

- This is a small FastAPI application with PyMongo-backed routers and a vanilla JavaScript frontend in `src/static/`.
- The application is run from the repository root with `python -m uvicorn src.app:app --reload`.
- There are currently no automated application tests; distinguish verified findings from untested assumptions and recommend focused tests when behavior changes.
- Keep the existing architecture and public API stable unless a change explicitly requires otherwise. Link to [the application README](../src/README.md) for the current API overview.

## Code Review Priorities

- Review the diff first, then inspect only the nearby call sites and configuration needed to validate a finding.
- Report concrete bugs, security risks, behavior regressions, and missing tests before style suggestions.
- For every finding, explain the affected behavior, its impact, and a specific fix. Include a file and line reference when possible.
- Do not report hypothetical issues without identifying a plausible input, execution path, or affected contract.
- Check whether API changes are reflected in `src/static/` and whether frontend changes preserve the backend contract.

## Security

- Validate and sanitize user-controlled input at the API boundary and before rendering it in the browser.
- Check authentication and authorization independently; the presence of a username or client-side state is not proof of permission.
- Look for credentials, personal data, or secrets exposed through URLs, logs, responses, hardcoded values, or browser storage.
- Prefer configuration and content from the database or environment variables over committed hardcoded values.
- Consider race conditions around capacity, registration, and other read-then-write operations.

## Code Quality

- Use consistent naming and the existing router/component boundaries.
- Prefer readable, maintainable changes over speculative optimization, while flagging repeated expensive work on hot paths.
- Prefer explicit error handling over silent failures and keep user-facing errors separate from sensitive server details.
- Verify semantic HTML, keyboard access, responsive behavior, and sufficient color contrast for frontend changes.