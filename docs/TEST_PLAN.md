# Test Plan

## Authentication

- User can sign up.
- User can log in.
- Invalid credentials show a useful error.
- User can log out.
- Logged-out users cannot access protected account pages.
- Sessions persist correctly.
- Password recovery flow is protected.

## Catalog

- Products load.
- Product detail pages load from valid slugs.
- Invalid product routes show a not-found state.
- Search returns matching products.
- Filters update results.
- Sorting is deterministic.
- Out-of-stock variants cannot be selected.

## Cart

- User can add an available product variant.
- User can update quantity.
- User can remove an item.
- Cart totals update correctly.
- Cart survives a page refresh according to the selected persistence strategy.
- Invalid or unavailable inventory cannot be purchased.

## Authorization

- Users can only read their own account data.
- Users cannot read another user's orders.
- Users cannot modify another user's cart.
- Server-side authorization remains enforced even if the UI is bypassed.

## Content

- Homepage sections render without broken media.
- FAQ expands and collapses accessibly.
- Newsletter form validates email input.
- Article links resolve to valid pages.

## Responsive

Test at:

- 375px
- 390px
- 768px
- 1024px
- 1440px

Verify:

- header navigation,
- product grids,
- hero composition,
- image cropping,
- buttons,
- forms,
- cart,
- footer,
- typography,
- horizontal overflow.

## Accessibility

- Keyboard navigation works.
- Focus states are visible.
- Images have meaningful alt text where required.
- Decorative images are ignored by assistive technology.
- Form labels are associated with inputs.
- Interactive controls have accessible names.
- Accordion state is announced appropriately.

## Performance

- Images use responsive optimization.
- Critical content is not blocked by non-essential client JavaScript.
- Avoid unnecessary hydration.
- Verify production build output before release.

## Acceptance

A feature is complete only when:

1. The implementation satisfies the relevant PRD requirement.
2. The UI follows `docs/DESIGN.md`.
3. Relevant tests pass.
4. Loading, error, empty, and success states are considered.
5. Security rules are respected.
6. `docs/MEMORY.md` is updated when project state changes.
