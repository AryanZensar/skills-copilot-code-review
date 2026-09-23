---
applyTo: "**/*.html,**/*.css,**/*.js"
---

## Frontend Review Guidelines

- Preserve valid semantic HTML structure and accessible names, labels, focus behavior, keyboard access, and appropriate ARIA only where needed.
- Check responsive layouts at narrow and wide viewports; new content must not overlap, cause unexpected overflow, or shift important controls.
- Check color contrast and do not rely on color, emoji, or hover state alone to communicate meaning.
- Treat all API data and user input as untrusted. Avoid unsafe `innerHTML` interpolation; use text nodes or sanitize content before rendering.
- Verify loading, empty, error, and authentication states when a change affects data fetching or user actions.
- Keep JavaScript selectors, endpoint paths, request methods, and response fields aligned with the FastAPI routers.