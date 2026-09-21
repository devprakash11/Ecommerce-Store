# Langkah. E-commerce Store

A premium, editorial sneaker e-commerce experience inspired by the provided visual reference. The product direction combines fashion editorial storytelling with a focused shopping flow.

## Product direction

**Brand:** Langkah.  
**Category:** Performance and lifestyle sneakers.  
**Primary experience:** Discover sneakers, explore collections, read editorial content, and move into a simple product-to-cart journey.

The reference uses an off-white editorial canvas, oversized typography, large product photography, asymmetric compositions, compact product grids, promotional banners, editorial cards, FAQ content, newsletter capture, and a dark footer.

## Recommended stack

- **AI IDE:** Antigravity
- **Frontend:** Next.js App Router
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **Database:** PostgreSQL via Supabase
- **Authentication:** Supabase Auth
- **Version control:** Git + GitHub
- **Testing:** Playwright
- **Deployment:** Vercel

## Repository structure

```text
Ecommerce-Store/
├── docs/
│   ├── PRD.md
│   ├── ARCHITECTURE.md
│   ├── DESIGN.md
│   ├── TEST_PLAN.md
│   ├── SECURITY.md
│   ├── DECISIONS.md
│   └── MEMORY.md
├── .antigravity/
│   └── rules/
│       ├── general.mdc
│       ├── frontend.mdc
│       ├── backend.mdc
│       └── testing.mdc
├── src/
│   ├── app/
│   ├── components/
│   ├── features/
│   ├── services/
│   ├── lib/
│   ├── types/
│   └── utils/
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── public/
├── .env.example
├── .gitignore
├── README.md
├── TASKS.md
└── package.json
```

## Documentation contract

- `docs/PRD.md` defines **what** is being built and **why**.
- `docs/ARCHITECTURE.md` defines **how** the application is structured.
- `docs/DESIGN.md` defines the visual and interaction system.
- `docs/DECISIONS.md` records permanent technical decisions.
- `docs/MEMORY.md` records the current implementation state.
- `TASKS.md` breaks implementation into small, testable units.
- `docs/TEST_PLAN.md` defines what working means.
- `docs/SECURITY.md` defines production security requirements.
- `.antigravity/rules/` provides AI implementation constraints.

## Getting started

The repository is intentionally scaffolded around the documentation-first workflow. After the project dependencies are installed:

```bash
npm install
npm run dev
```

Create `.env.local` from `.env.example` before enabling Supabase-backed functionality.

## Development principle

Build in small vertical slices:

```text
TASK
  ↓
Implement
  ↓
Test
  ↓
Review
  ↓
Mark complete
  ↓
Next TASK
```

Do not treat the entire storefront as one implementation prompt.
