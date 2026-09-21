# Architecture

## Runtime flow
Browser -> Next.js App Router -> Server Component / Route Handler / Action -> Service Layer -> Supabase -> PostgreSQL/Auth/Storage.

## Source boundaries
- app: routing and composition only
- components: reusable visual building blocks
- features: domain behavior and client state
- services: database/integration access
- lib: infrastructure
- types: shared contracts
- data: development seed content
- styles: global design system

Prefer Server Components. Use Client Components only for browser state or interaction. Keep privileged credentials server-only. Do not put SQL or Supabase queries in visual components.

## Commerce model
products, product_variants, profiles, orders and order_items are the initial relational entities. Inventory, prices and authorization remain server-owned data.

## Rendering
Use URL search parameters for shareable filters. Use responsive images in production. Provide loading, empty, error and success states on interactive flows.