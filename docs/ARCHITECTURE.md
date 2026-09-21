# Architecture

## Stack

### Frontend

Next.js with the App Router and TypeScript.

### Styling

Tailwind CSS with a shared design token layer documented in `docs/DESIGN.md`.

### Backend

Next.js server-side functionality using Server Components, Server Actions, Route Handlers, and server-only services where appropriate.

### Database

Supabase PostgreSQL.

### Authentication

Supabase Auth using secure server-side session handling.

### Storage

Supabase Storage for product and editorial media where database-backed media management is required.

### Testing

Playwright for end-to-end coverage. Unit and integration tests should be added around business-critical utilities and services.

### Deployment

Vercel.

## Request flow

```text
Browser
  ↓
Next.js App Router
  ↓
Server Component / Server Action / Route Handler
  ↓
Service Layer
  ↓
Supabase Client
  ↓
PostgreSQL / Storage / Auth
```

## Folder structure

```text
src/
├── app/
│   ├── (store)/
│   ├── account/
│   ├── cart/
│   ├── checkout/
│   ├── collections/
│   ├── products/
│   ├── search/
│   ├── api/
│   ├── layout.tsx
│   └── page.tsx
├── components/
│   ├── ui/
│   ├── layout/
│   ├── commerce/
│   └── content/
├── features/
│   ├── auth/
│   ├── cart/
│   ├── catalog/
│   ├── collections/
│   ├── checkout/
│   ├── content/
│   └── account/
├── services/
│   ├── products/
│   ├── collections/
│   ├── cart/
│   ├── orders/
│   ├── content/
│   └── users/
├── lib/
│   ├── supabase/
│   ├── validation/
│   ├── constants/
│   └── config/
├── types/
└── utils/
```

## Application routes

```text
/
├── /collections
├── /collections/[slug]
├── /products
├── /products/[slug]
├── /search
├── /cart
├── /checkout
├── /account
├── /account/orders
├── /account/orders/[id]
├── /about
├── /journal
└── /journal/[slug]
```

## Data model direction

Initial entities:

- `profiles`
- `products`
- `product_variants`
- `product_images`
- `collections`
- `collection_products`
- `categories`
- `carts`
- `cart_items`
- `orders`
- `order_items`
- `wishlists`
- `wishlist_items`
- `articles`
- `faqs`
- `newsletter_subscribers`

Use normalized relational data for commerce state. Do not duplicate product prices, inventory, or ownership rules across UI components.

## Rendering rules

- Prefer Server Components.
- Use Client Components only for browser state or event-driven interaction.
- Keep database credentials and privileged operations server-only.
- Use URL search parameters for shareable catalog filters.
- Use optimistic UI only where rollback behavior is well-defined.
- Use `next/image` for local or remote images configured through approved domains.

## Service boundary

UI components call feature-level actions or services. UI components should not directly contain SQL or Supabase table queries.

Example:

```text
ProductCard
  ↓
Catalog feature
  ↓
Product service
  ↓
Supabase
```

## Architectural rules

- UI components must not contain database logic.
- Database operations belong in services.
- Authorization must be verified server-side.
- Reusable primitives belong in `components/ui`.
- Domain-specific behavior belongs in `features`.
- External integrations belong behind service boundaries.
- Shared types belong in `types`.
- Pure helper functions belong in `utils`.
- Environment access belongs in `lib/config`.
- Do not introduce a second backend framework unless a documented decision changes this architecture.
