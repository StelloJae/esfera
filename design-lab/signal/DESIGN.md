# Signal — Design Spec
**Direction:** Bold Film-Title / Manifesto Poster

---

## North-Star Signature
Pure-black stage. One mint accent used only as solid fill — not as a glow, border, or tint. Typography is the only decoration: massive grotesque display that hits like a wall, monospace body that reads like a terminal. Dramatic emptiness between sections is structural.

---

## Color Tokens

| Token | Hex | Role |
|---|---|---|
| `--black` | `#000000` | Canvas, nav bg, page background |
| `--white` | `#ffffff` | Primary text, headlines |
| `--off` | `#111111` | Alternate dark surface |
| `--mid` | `#2a2a2a` | Section rule backgrounds |
| `--dim` | `#5a5a5a` | Section labels, eyebrows |
| `--muted` | `#888888` | Body copy |
| `--accent` | `#3cffd0` | **Solid fill only** — hero headline block, pullquote keyword, flagship header band, dot mark |
| `--accent-dim` | `#0a3329` | Reserved for future accent-on-dark surfaces |

**Accent-as-Fill Rule:** The accent `#3cffd0` is applied exclusively as a solid block fill (`background: #3cffd0; color: #000`). It is never used as a stroke, a gradient stop, a text color on dark, or a glow. One fill element per section, maximum.

---

## Type Tokens

| Role | Family | Size | Weight | Transform | Tracking |
|---|---|---|---|---|---|
| Display / Headline | Archivo Black | `clamp(3.5rem, 10vw, 9rem)` | 900 | UPPERCASE | `-0.02em` |
| Sub-headline | Archivo Black | `clamp(1.8rem, 4.5vw, 4rem)` | 900 | UPPERCASE | `-0.01em` |
| Section title | Archivo Black | `clamp(2rem, 4vw, 3.5rem)` | 900 | UPPERCASE | `-0.01em` |
| Principle label | Archivo Black | `clamp(1rem, 1.8vw, 1.4rem)` | 900 | UPPERCASE | `-0.01em` |
| Body / lede | Space Mono | `clamp(14px, 1.5vw, 17px)` | 400 | none | 0 |
| Eyebrow / label | Space Mono | `11px` | 700 | UPPERCASE | `0.2em` |
| Nav links | Space Mono | `11px` | 400 | UPPERCASE | `0.12em` |

Line height: `0.95` for display, `1.7–1.85` for body.

---

## Spacing & Radius

- **Section padding:** `7rem 2.5rem` (desktop), `5rem 1.25rem` (mobile)
- **Nav height:** `~64px` (fixed)
- **Section dividers:** `1px solid #1a1a1a` — horizontal lines only
- **Grid gaps:** `3rem` (2-col layouts), `5rem` (label + content layouts)
- **Border radius:** `0px` everywhere. No rounding.
- **No shadows.** No gradients. No blur.

---

## Do / Don't

**Do:**
1. Use `--accent` as a single solid fill block per section — the flagship header band or a word callout, never both at once
2. Let huge type do the decorative work; whitespace is the reset between loud moments
3. Keep body copy in Space Mono at muted gray (`#888–#c0c0c0`); only highlights go `#fff`
4. Use numbered counters (01, 02, 03) in Space Mono for lists — they signal structure without visual noise

**Don't:**
1. Add the accent color as a border, text color, or gradient on dark surfaces
2. Round any corners — 0px radius is load-bearing to the aesthetic
3. Introduce a second accent or decorative color (purple, blue, warm tones)
4. Use inline SVG decorative art or icons beyond the sphere mark

---

## Iteration Guide
To dial intensity: increase hero headline `clamp` upper bound for more drama; decrease body copy brightness toward `#666` for more contrast-punch on key highlights.

---

## Known Gaps
- No scroll-based animation (intentional — static file constraint); could be added with pure CSS `@keyframes` if desired
- Flagship section accent band could become a horizontal "tape" spanning full-bleed on very wide viewports (>1600px) — currently clips at right edge
- Nav on mobile hides all links; a hamburger menu or bottom-fixed strip would be needed for production
