# Security Requirements

## Authentication

- Private routes require authentication.
- Session state must be validated server-side.
- Do not trust user identity values supplied by the browser.

## Authorization

- Users can only access resources they own.
- Enforce ownership through server-side checks and Supabase Row Level Security.
- Do not rely only on hidden UI controls for authorization.

## Secrets

Never commit:

- Supabase service-role keys.
- Database passwords.
- Payment provider secret keys.
- Private API credentials.
- `.env.local`.

Only public client-safe variables may be exposed to browser code.

## Database

- Enable RLS for user-owned tables.
- Define explicit policies.
- Use foreign keys and constraints.
- Validate expected enum/status values.
- Do not expose unrestricted database access.

## Input validation

Validate:

- authentication fields,
- product identifiers,
- quantity values,
- addresses,
- checkout data,
- newsletter email addresses,
- query parameters,
- API request bodies.

Use schema validation at trust boundaries.

## APIs and Server Actions

- Authenticate before protected operations.
- Authorize resource ownership.
- Validate parameters.
- Return safe errors without leaking secrets or internal database details.
- Rate-limit sensitive endpoints when appropriate.

## File uploads

Validate:

- file type,
- file size,
- file name,
- storage path,
- user authorization.

Do not trust MIME type alone for security-sensitive uploads.

## Commerce integrity

- Never calculate final order totals solely from client-supplied values.
- Re-read authoritative product pricing and inventory server-side.
- Treat cart contents from the client as untrusted input.
- Prevent negative quantities and invalid variants.

## Security review

Before production:

- Review RLS policies.
- Review environment variables.
- Review authentication callbacks.
- Review upload policies.
- Review checkout/order creation.
- Run dependency and build checks.
