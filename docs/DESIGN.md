# Design System

## Design direction

The visual language is **editorial sneaker commerce**: minimal, confident, image-led, functional, and slightly athletic.

The supplied reference is the source of truth for the initial art direction.

## Brand

**Name:** Langkah.

The brand should feel contemporary and movement-oriented without becoming visually aggressive.

## Visual principles

- Large typography with generous whitespace.
- Off-white surfaces instead of a default pure-white SaaS canvas.
- Strong black typography for contrast.
- Product imagery carries most of the visual color.
- Asymmetric editorial layouts are encouraged in hero and content sections.
- Product grids remain structured and easy to scan.
- Use thin borders and restrained shadows.
- Avoid excessive rounded cards.
- Avoid gradients unless specifically required by campaign artwork.
- Avoid generic dashboard-style UI patterns.

## Color tokens

```text
Canvas:       #F3F0EA
Surface:      #ECE8E1
Surface Dark: #1C1C1C
Text:         #171717
Muted:        #6F6A63
Border:       #D8D2C9
White:        #FFFFFF
Accent Blue:  #2D5BFF
Accent Lime:  #B9D93C
Accent Cyan:  #5CC7D8
```

Product photography may introduce additional colors, but those colors should not automatically become interface tokens.

## Typography

Preferred type direction:

- Display: modern grotesk or condensed sans-serif.
- Body: neutral sans-serif.
- Utility/meta: compact uppercase sans-serif with tracking.

Recommended implementation can use a Next.js optimized font pairing. The final font choice must preserve:

- high x-height body readability,
- strong large display numerals,
- clear uppercase navigation,
- compact product metadata.

## Type scale

```text
Display XL:  clamp(3.5rem, 10vw, 8rem)
Display L:   clamp(2.75rem, 7vw, 5.5rem)
Heading XL:  clamp(2rem, 4vw, 3.75rem)
Heading L:   clamp(1.75rem, 3vw, 2.75rem)
Heading M:   clamp(1.25rem, 2vw, 1.75rem)
Body:        0.95rem - 1rem
Small:       0.75rem - 0.875rem
Micro:       0.625rem - 0.75rem
```

## Layout

Desktop:

- Max content width: approximately 1320px.
- 12-column grid where editorial compositions need it.
- Consistent horizontal gutters.
- Large vertical rhythm between major sections.

Mobile:

- 16px to 20px side gutters.
- Single-column content by default.
- Two-column product grids where product imagery remains legible.
- Horizontally scrollable content only when it improves discovery and has visible affordance.

## Header

Reference direction:

- Wordmark on the left.
- Primary navigation centered or visually balanced.
- Utility actions on the right.
- Compact typography.
- Sticky behavior may be introduced after the base layout is stable.

## Buttons

### Primary

- Dark background.
- White text.
- Compact uppercase label.
- Minimal radius.
- Strong hover/focus state.

### Secondary

- Transparent or surface background.
- Dark text.
- Thin border when a boundary is required.

### Destructive

- Reserved for irreversible actions.
- Never use destructive styling for ordinary shopping actions.

## Product cards

Each card should support:

- Product image.
- Product name.
- Short category or style label.
- Price.
- Availability state.
- Add-to-cart action where appropriate.

Keep product cards visually quiet so the product photography remains dominant.

## Editorial sections

Use:

- Full-bleed imagery.
- Large captions.
- Short copy blocks.
- Small metadata labels.
- Directional arrow affordances.

Do not overload editorial cards with badges.

## FAQ

Accordion rows should be compact and editorial:

- question on the left,
- chevron on the right,
- clear focus state,
- only one expanded item when that behavior supports scanning.

## Forms

- Visible labels.
- Clear validation.
- Useful error messages.
- Keyboard navigation.
- No placeholder-only labels.

## Motion

Motion should be subtle:

- 150-250ms interaction transitions.
- Image scale on hover may be used sparingly.
- Page transitions should not block navigation.
- Respect `prefers-reduced-motion`.

## Responsive UX requirements

Every page must define:

- loading state,
- empty state,
- error state,
- success state where relevant,
- keyboard behavior,
- touch target size,
- focus visibility.

## Accessibility

Target WCAG 2.2 AA where practical:

- sufficient text contrast,
- semantic landmarks,
- accessible names,
- keyboard navigation,
- visible focus,
- alt text for meaningful images,
- decorative images marked appropriately.
