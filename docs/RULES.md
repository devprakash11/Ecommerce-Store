# Development Rules

## General

- Use TypeScript.
- Reuse existing components.
- Do not duplicate business logic.
- Keep functions focused.
- Do not modify unrelated files.
- Follow the repository documentation before introducing new patterns.

## Before coding

1. Read the relevant documentation.
2. Inspect the existing implementation.
3. Identify reusable functionality.
4. Make a plan for large changes.
5. Implement the smallest coherent change.

## UI

- Follow `docs/DESIGN.md`.
- Keep the storefront responsive.
- Preserve the editorial visual language.
- Add loading states.
- Add error states.
- Add empty states.
- Use semantic HTML.
- Do not introduce arbitrary colors or component styles.

## Data

- UI code must not contain raw database queries.
- Use service functions for data access.
- Validate external and user-provided data.
- Keep server-only code server-only.

## Security

- Never commit secrets.
- Never expose service-role credentials to the browser.
- Validate authorization server-side.
- Apply database policies to user-owned data.
- Validate uploads and request payloads.

## Testing

- Add tests for critical behavior.
- Run relevant tests after implementation.
- Fix failing tests before marking a task complete.
- Critical checkout and authorization paths require end-to-end coverage.

## Git

- Make small, focused commits.
- Use descriptive commit messages.
- Avoid unrelated formatting changes.
- Do not commit `.env.local`.
- Keep architectural changes documented in `docs/DECISIONS.md`.

## AI implementation rule

The AI must not silently replace the documented stack, architecture, or design system. If a change requires an architectural decision, document it first.
