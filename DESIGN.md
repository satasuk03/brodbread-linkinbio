# BRÖD — Design System

Retro, two-color letterpress bakery identity. Warm, hand-drawn, always-running charm. We sell sourdough.

**Owner-pinned.** Applies to every Bröd Bread surface — marketing site, packaging artwork, and the CRM dashboard. Deviations need the owner's sign-off, not a designer's judgment call.

---

## 1. Color

Two inks on cream. That's the whole system.

| Token | Hex | Role |
| --- | --- | --- |
| Bakehouse Red | `#C41D12` | Headlines, mascot, primary buttons, urgent / warn states |
| Sky Blue | `#5597CD` | Accents, tags, links, secondary strokes, tagline, info states |
| Cream Paper | `#F8EFEB` | Default background for everything |
| Ink Brown | `#2B1A15` | Keylines, text, hard shadows |
| Soft Ink | `#5B463E` | Body copy, secondary text — **on cream only** |
| Blue Tint | `#EEF5FB` | Panel tint |

**Rules**

- Never use gradients as color fills. (Gradients are allowed only as *texture* — see Retro treatment.)
- Never put full color on the mascot.
- Max 1–2 background colors per surface.
- Soft Ink is a cream-only color; on red or blue, text goes cream.

## 2. Typography

| Use | Face | Weight | Size |
| --- | --- | --- | --- |
| Hero | Unbounded | 700–900 | ~72px |
| Section title | Unbounded | 700–900 | 36px |
| Subhead | Unbounded | 600 | — |
| Subtitle | Unbounded | 700–900 | 20px |
| Body / UI / labels | IBM Plex Sans | 400–700 | 16px |
| Spec captions, codes, labels | IBM Plex Mono | 500 | 12px, `.14em` letter-spacing, uppercase |

**Thai text** falls back to system Thai faces (Sarabun / Noto Sans Thai) — Unbounded and Plex ship no Thai glyphs. Numerals and Latin still render in the brand faces, so a mixed line stays on-brand.

## 3. Retro treatment

- **Thick keylines** — 3px `#2B1A15` borders on cards, badges, buttons.
- **Hard offset shadows** — `box-shadow: 8px 8px 0` ink brown (or a faint tint), no blur. Primary buttons press down into their shadow on hover.
- **Halftone dots** — `radial-gradient` dot fields for texture. Subtle, on cream surfaces.
- **Diagonal stripes** — `repeating-linear-gradient` at 45°, for awning edges and in-progress fills.
- **Sunburst rays** — `repeating-conic-gradient` behind the hero, faint red on cream.
- **Shapes** — rounded pills, dashed circular stamps, starburst badges, and slight rotations (±1–2°) on stickers and stamps.

## 4. Components

| Component | Spec |
| --- | --- |
| Button — primary | Pill, 3px ink border, red fill, cream text. Presses into its shadow on hover. |
| Button — secondary | Pill, 3px ink border, blue outline; fills on hover. |
| Button — tertiary | Underline link. |
| Tag / chip | Pill. Active = red fill; inactive = blue outline; neutral = ink outline. |
| Input | Pill, 3px ink border, cream or white field. |
| Price stamp | Red dashed circle, price set in Unbounded. |
| Panel / card | Cream body, 3px ink keyline, hard 8px offset shadow. Optional red header bar. |

## 5. Mascot

`brod-mascot.png` — **Crumb**, running left → right, paired with the wordmark.

- Don't recolor, drop-shadow, stretch, skew, or rotate the artwork.
- One ink only in reproductions: red on cream, cream on red, or blue on cream.
- Clear space ≈ one bun-height on all sides.
- Never reproduce below 44px tall.

## 6. Voice

Warm, playful, unfussy. Short and friendly — reads like a hand-stamped label.

On the CRM, **UI copy stays in Thai**; brand marks (BRÖD, the tagline) stay Latin.

---

## Tokens

```css
:root {
  /* Color */
  --brod-red:        #C41D12;  /* Bakehouse Red */
  --brod-blue:       #5597CD;  /* Sky Blue */
  --brod-cream:      #F8EFEB;  /* Cream Paper — default background */
  --brod-ink:        #2B1A15;  /* Ink Brown — keylines, text, shadows */
  --brod-soft-ink:   #5B463E;  /* Soft Ink — body copy, on cream only */
  --brod-blue-tint:  #EEF5FB;  /* Blue Tint — panel tint */

  /* Retro treatment */
  --brod-keyline:    3px solid var(--brod-ink);
  --brod-shadow:     8px 8px 0 var(--brod-ink);

  /* Type — Thai fallbacks carry glyphs the brand faces lack */
  --brod-font-display: "Unbounded", "Sarabun", "Noto Sans Thai", sans-serif;
  --brod-font-body:    "IBM Plex Sans", "Sarabun", "Noto Sans Thai", sans-serif;
  --brod-font-mono:    "IBM Plex Mono", "Sarabun", "Noto Sans Thai", monospace;

  /* Scale */
  --brod-text-hero:     72px;
  --brod-text-section:  36px;
  --brod-text-subtitle: 20px;
  --brod-text-body:     16px;
  --brod-text-caption:  12px;
  --brod-caption-track: .14em;
}
```

### Texture recipes

Starting points — tune density per surface, keep them faint.

```css
/* Halftone dots — subtle texture on cream */
background-image: radial-gradient(var(--brod-ink) 1px, transparent 1px);
background-size: 6px 6px;
opacity: .08;

/* Diagonal stripes — awning edges, in-progress fills */
background-image: repeating-linear-gradient(
  45deg, var(--brod-red) 0 8px, transparent 8px 16px
);

/* Sunburst rays — behind the hero, faint red on cream */
background-image: repeating-conic-gradient(
  var(--brod-red) 0deg 4deg, transparent 4deg 12deg
);
```

## Never

- Gradients as color fills.
- Full color on the mascot; recoloring, skewing, stretching, or rotating it.
- Mascot below 44px tall.
- More than two background colors on one surface.
- Soft Ink on anything but cream.
- Blur on a shadow.
