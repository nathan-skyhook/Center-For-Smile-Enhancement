# Design System — Center for Smile Enhancement

## Brand Direction

Premium, editorial, warm. Target demographic is adults 45+, fee-for-service patients who prioritize quality over cost. Think Nordstrom editorial pages or Ritz-Carlton print materials — refined but never cold. Heavy white space, open contemporary feel.

---

## Colors

### Brand Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-primary` | `#1e3460` | Headings, CTA buttons, nav, key UI elements |
| `--color-primary-hover` | `#162850` | Button hover states |
| `--color-brand-light` | `#c5cde3` | Accents, section dividers, tag/badge backgrounds, card top borders |

### Text Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-text-base` | `#1a1f2e` | Body copy, primary text |
| `--color-text-muted` | `#6b7280` | Secondary text, descriptions, captions |

### Backgrounds

| Token | Hex | Usage |
|-------|-----|-------|
| `white` | `#ffffff` | Primary page background, card backgrounds |
| `--color-surface` | `#f8f9fb` | Section alternation, hero, 404 bg |
| `--color-border` | `#e4e8f0` | Card borders, dividers, nav border |
| `--color-primary` | `#1e3460` | Dark CTA sections, footer |
| `--color-brand-light` | `#c5cde3` | Patient resources section background |

### Semantic Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-success` | `#10b981` | Success states |
| `--color-warning` | `#f59e0b` | Star ratings (5-star yellow) |
| `--color-error` | `#ef4444` | Error states |
| `--color-info` | `#3b82f6` | Info states |

---

## Typography

### Fonts

**Playfair Display** — Display/Heading font
- Weights: 600 (Semibold), 700 (Bold)
- `font-family: var(--font-display)` or CSS token `--font-display`
- Google Fonts URL: `https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&display=swap`

**Lato** — Body/UI font
- Weights: 300 (Light), 400 (Regular), 500 (Medium)
- `font-family: var(--font-body)` or CSS token `--font-body`
- Google Fonts URL: `https://fonts.googleapis.com/css2?family=Lato:wght@300;400;500&display=swap`

### Type Scale

| Element | Font | Size | Weight |
|---------|------|------|--------|
| H1 (hero) | Playfair Display | `clamp(2.25rem, 5vw, 3.75rem)` | 700 |
| H2 (section) | Playfair Display | `clamp(1.75rem, 3vw, 2.5rem)` | 700 |
| H3 (card) | Playfair Display | `1rem–1.125rem` | 600 |
| Body | Lato | `0.9375rem–1rem` | 400 |
| Eyebrow labels | Lato | `0.75rem` | 500, uppercase, tracked |
| Button text | Lato | `0.8125rem` | 500, uppercase, tracked |
| Small/captions | Lato | `0.8125rem` | 300–400 |

### Usage Rules

- H1–H2: Playfair Display 700
- H3–H4: Playfair Display 600
- H5–H6: Lato 500, uppercase, tracked
- Body: Lato 400, line-height 1.65–1.75
- CTAs/Buttons: Lato 500, `letter-spacing: 0.09em`, uppercase

---

## Buttons

Three variants, defined as CSS component classes:

```html
<!-- Primary: dark navy fill -->
<a href="..." class="btn btn-primary">Schedule Appointment</a>

<!-- Outline: dark navy border, transparent fill (inverts on hover) -->
<a href="..." class="btn btn-outline">Learn More</a>

<!-- Outline White: white border for dark backgrounds -->
<a href="..." class="btn btn-outline-white">Contact Us</a>
```

Spec: 2px solid border, `padding: 0.8125rem 1.875rem`, uppercase tracking, 0.2s transition.

---

## Layout

### Container

Use `.site-container` for all sections:
```html
<div class="site-container">...</div>
```
- Max-width: 1280px
- Padding: 1.5rem mobile → 2rem tablet → 2.5rem desktop

### Section Padding

Use `.section-py` for standard vertical section spacing:
- Mobile: `4rem` top/bottom
- Tablet: `5rem`
- Desktop: `6rem`

### Homepage Section Color Alternation

| Section | Background |
|---------|-----------|
| Hero | `#ffffff` |
| Trust strip | `--color-surface` |
| What Sets Us Apart | `#ffffff` |
| Services | `--color-surface` |
| Testimonials | `#ffffff` |
| Patient Resources | `--color-brand-light` |
| Final CTA | `--color-primary` (dark navy) |
| Footer | `--color-primary` (dark navy) |

---

## Cards

Use `.card` class for standard bordered cards:
```html
<div class="card">...</div>
```
- White background
- 1px border using `--color-border`
- `padding: 1.75rem`
- Hover: subtle shadow lift + 2px translate up

Feature cards get a `border-top: 3px solid var(--color-brand-light)` accent.

---

## Spacing Conventions

- Section vertical padding: see `.section-py`
- Card padding: `1.5rem–1.75rem`
- Between section heading and content: `3rem–3.5rem`
- Between elements within a card: `0.5rem–1rem`
- Button gaps: `1rem`

---

## Grid Patterns

### Features (2→4 columns)
```
mobile: 1 col
sm: 2 col
lg: 4 col
```

### Services (1→2→3→5 columns)
```
mobile: 1 col
sm: 2 col
lg: 3 col
xl: 5 col
```

### Testimonials (1→3 columns)
```
mobile: 1 col
md: 3 col
```

### Patient Resources (1→2→4 columns)
```
mobile: 1 col
sm: 2 col
lg: 4 col
```

### Footer (1→2→4 columns)
```
mobile: 1 col
sm: 2 col (brand spans 2)
lg: 1.5fr + 3×1fr
```

---

## Accessibility

- Color contrast: all text/bg combinations meet WCAG 2.1 AA (4.5:1 for body, 3:1 for large text)
- Primary (`#1e3460`) on white: ~12.2:1 ✓
- Muted (`#6b7280`) on white: ~4.8:1 ✓ (borderline; prefer `--color-text-base` for critical copy)
- White on primary (`#1e3460`): ~12.2:1 ✓
- **⚠ Warning:** `--color-text-muted` (`#6b7280`) on `--color-brand-light` (`#c5cde3`) = 3.04:1 — **WCAG AA FAIL** for body text. Never place muted text directly on the brand-light background. Use `--color-primary` or `--color-text-base` for any text on brand-light sections. The Patient Resources section `section-eyebrow` works because it includes an explicit `style="color: var(--color-primary)"` override.
- All interactive elements have visible focus states
- SVG icons include `aria-hidden="true"` when decorative
- Semantic HTML: `<header>`, `<main>`, `<footer>`, `<nav>`, `<section aria-labelledby>`, `<article>`

---

## Component Conventions

- Components in `src/components/` use PascalCase
- Inline styles for dynamic/per-instance values, CSS classes for structural patterns
- `<style>` block per component for component-scoped responsive rules
- No Tailwind utility classes in `.astro` template markup for layout — use semantic CSS classes from `global.css` instead
- Images: always provide `width`, `height`, `loading`, and `alt`; hero image uses `loading="eager" fetchpriority="high"`
