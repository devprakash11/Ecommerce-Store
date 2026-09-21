# Architecture Decisions

## ADR-001: Use Next.js App Router

**Decision:** Use Next.js as the unified frontend and server application layer.

**Reason:** The storefront benefits from server rendering, route-level data loading, metadata, image optimization, and server-side application logic without introducing a separate Express application.

**Status:** Accepted

## ADR-002: Use TypeScript

**Decision:** Use TypeScript throughout application code.

**Reason:** Product, cart, order, and authentication domains contain structured data where compile-time contracts reduce integration errors.

**Status:** Accepted

## ADR-003: Use Supabase

**Decision:** Use Supabase for PostgreSQL, authentication, and storage.

**Reason:** It provides the required relational database, authentication, storage, and row-level security capabilities in one platform.

**Status:** Accepted

## ADR-004: Use Tailwind CSS

**Decision:** Use Tailwind CSS with a project design-token layer.

**Reason:** The project requires consistent responsive styling and a controlled visual system across many storefront sections.

**Status:** Accepted

## ADR-005: Use Vercel

**Decision:** Deploy the application on Vercel.

**Reason:** The application is built around Next.js and benefits from integrated deployment and preview environments.

**Status:** Accepted

## ADR-006: Server-first data access

**Decision:** Keep privileged database access on the server.

**Reason:** Secrets and authorization rules must not be exposed to the browser. UI components should consume server-safe services or actions.

**Status:** Accepted

## ADR-007: Documentation-first AI workflow

**Decision:** Use PRD, Architecture, Design, Rules, Tasks, Decisions, Memory, Test Plan, and Security documentation as the project operating system.

**Reason:** This reduces architectural drift and makes AI-assisted development repeatable.

**Status:** Accepted
