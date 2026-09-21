# Langkah. E-commerce Store

A professional editorial sneaker e-commerce storefront built from the supplied visual direction.

## Stack
Next.js App Router, TypeScript, Tailwind CSS v4, Supabase PostgreSQL/Auth, Zustand, Playwright, Vercel.

## Run
```bash
npm install
cp .env.example .env.local
npm run dev
```

## Architecture
```
src/app          -> routes and page composition
src/components   -> reusable UI and commerce presentation
src/features     -> domain/client behavior
src/services     -> data-access boundary
src/lib          -> Supabase, config and shared infrastructure
src/types        -> shared TypeScript contracts
src/data         -> initial typed demo catalog/content
src/styles       -> design tokens and global styling
supabase         -> migrations and seed data
tests            -> Playwright coverage
```

The first storefront slice works without Supabase by using typed local catalog data. The service layer is the replacement point for PostgreSQL-backed catalog queries.

## Production steps
1. Add Supabase environment variables.
2. Apply `supabase/migrations/0001_initial_schema.sql`.
3. Replace demo auth forms with Supabase Auth actions.
4. Replace checkout scaffold with a server-side payment integration and verified webhooks.
5. Move product/editorial media into production storage.
6. Publish final legal, shipping and returns policies.
7. Run `npm run typecheck`, `npm run lint` and `npm run test:e2e`.
8. Deploy to Vercel.

Never commit `.env.local` or service-role credentials.