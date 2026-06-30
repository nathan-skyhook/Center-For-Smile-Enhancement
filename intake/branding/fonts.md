# Brand Typography — Center for Smile Enhancement

## Design Direction
Premium, editorial, warm. Target demographic is 45+, fee-for-service patients.
Think Nordstrom editorial pages or Ritz-Carlton print materials — refined but never cold.

---

## Font Families

### Display Font (Headings, Hero Text)
**Font:** Playfair Display
**Weights:** 600 (Semibold), 700 (Bold)
**Google Fonts URL:** `https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&display=swap`
**Rationale:** Classic editorial serif — conveys quality, trust, and warmth. Widely used in premium healthcare and luxury hospitality. Strong at large sizes; stands out against clean white space.

### Body Font (Paragraphs, UI, Navigation)
**Font:** Lato
**Weights:** 300 (Light), 400 (Regular), 500 (Medium)
**Google Fonts URL:** `https://fonts.googleapis.com/css2?family=Lato:wght@300;400;500&display=swap`
**Rationale:** Clean, warm sans-serif with excellent screen readability. Humanist letterforms (approachable, not corporate). Pairs naturally with Playfair Display. Proven for 45+ demographics — clear without feeling clinical.

---

## Combined Load URL

```
https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Lato:wght@300;400;500&display=swap
```

---

## Usage Guidelines

- **H1–H2:** Playfair Display 700
- **H3–H4:** Playfair Display 600
- **H5–H6:** Lato 500 (uppercase tracking for subheadings)
- **Body text:** Lato 400
- **Captions, labels:** Lato 300 or 400
- **CTAs/buttons:** Lato 500, tracked slightly wide

## Font Loading Strategy

Loaded via Google Fonts with `display=swap` to prevent layout shift.
System font fallbacks: Georgia (display), system-ui (body).
