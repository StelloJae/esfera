# D-b — Design Spec
**Direction:** Bold Manifesto Poster — Warm Accent + Fluid Scaling
**Base:** D / Signal

---

## What Changed from D (Signal)

| Dimension | D (Signal) | D-b |
|---|---|---|
| Accent | `#3cffd0` mint | `#d2562a` warm terracotta |
| Scaling | Fixed px breakpoints | Fluid: root `clamp()` + rem/em throughout |
| Shell | Full-width, fixed padding | `min(94vw, 88rem)` centered, fluid padding |
| Dark mode | Dark only | Dark only (unchanged) |
| Everything else | — | Unchanged |

---

## Color Tokens

| Token | Hex | Role |
|---|---|---|
| `--black` | `#000000` | Canvas, nav bg, page background |
| `--white` | `#ffffff` | Primary text, headlines |
| `--dim` | `#5a5a5a` | Section labels, eyebrows |
| `--accent` | `#d2562a` | **Solid fill only** — hero headline block, pullquote keyword, flagship header band |
| `--accent-on` | `#c0471d` | Dot mark, small accent details |

**Accent-as-Fill Rule (inherited from D):** `#d2562a` is applied exclusively as a solid block fill (`background: #d2562a; color: #000`). Never a stroke, gradient stop, text color on dark, or glow. One fill element per section, maximum.

**Warm accent note:** `#d2562a` (terracotta) is used for large solid fills on pure black — slightly lighter than `#c0471d` so the fill reads with confidence at full band width. `#c0471d` reserved for small marks (dot).

---

## Type Tokens

Same as D / Signal — unchanged.

| Role | Family | Weight | Transform |
|---|---|---|---|
| Display / Headline | Archivo Black | 900 | UPPERCASE |
| Body / lede | Space Mono | 400 | none |
| Eyebrow / label | Space Mono | 700 | UPPERCASE |

---

## Responsive — Fluid Scaling

D-b replaces D's fixed-px breakpoint-only approach with a proportional fluid system:

```css
/* Root font-size: ~15px @ 360px → ~22px @ ~1700px */
html { font-size: clamp(15px, calc(0.45vw + 13px), 22px); }

/* Shell: uses full screen proportionally on wide displays */
.shell { width: min(94vw, 88rem); margin-inline: auto; }

/* Side padding scales proportionally */
.padded { padding-inline: clamp(1.25rem, 3vw, 2.5rem); }

/* Hero headline: huge + scales with viewport AND root */
.hero-headline { font-size: clamp(3rem, 9vw, 11rem); }
```

All sizing uses `rem`/`em` so every dimension scales automatically with root.
Layout breakpoints (grid collapses) remain at `900px` and `640px` — they handle
structure only, not font sizes.

---

## Spacing & Radius

- **Border radius:** `0px` everywhere. No rounding.
- **No shadows.** No gradients. No blur.
- **Section dividers:** `1px solid #1a1a1a`
- **Section padding:** fluid via `clamp()` — `clamp(4rem, 8vw, 7rem)` vertical

---

## Do / Don't

Inherits all rules from D / Signal, plus:

**Do:**
- Use `#d2562a` for large solid fills on black — it reads warm and confident
- Keep `#c0471d` for the sphere mark dot (slightly deeper = holds weight at small size)
- Let the fluid root scale do the work — author sizes in rem, not px

**Don't:**
- Introduce light mode — this is a black poster, dark only
- Add the accent as a border or text color on dark surfaces
- Round corners
