# DESIGN.md — Esfera Research / Austere Brutalist Lab

**North star:** A precise lab notice-board printed on near-black — every element earns its place or gets cut; the single acid spark signals life without decoration.

---

## Color Tokens

| Token | Hex | Role |
|---|---|---|
| `--black` | `#0a0a0a` | Page canvas, only background |
| `--white` | `#f0f0ee` | Primary text, headlines |
| `--dim` | `#888888` | Secondary text, labels, nav at rest |
| `--body` | `#bbbbbb` | Body copy — readable, not bright |
| `--hairline` | `#222222` | All dividers, borders, grid lines |
| `--surface` | `#0f0f0f` | Elnath block inset — barely lifted |
| `--acid` | `#d4ff00` | Sphere mark, Elnath left-border, footer dot. Nowhere else. |

---

## Type Tokens

| Role | Font | Size | Weight | Tracking |
|---|---|---|---|---|
| Display / H1 | Space Grotesk | clamp(48px → 88px) | 700 | -0.03em |
| H2 (Elnath, Day Zero) | Space Grotesk | clamp(20px → 32px) | 700 | -0.02em |
| Pull quote | Space Grotesk | clamp(20px → 32px) | 500 | -0.015em |
| Body | Space Grotesk | 16–17px | 400 | 0 |
| Lede | Space Grotesk | clamp(16px → 20px) | 400 | 0 |
| Eyebrow / Section label | Space Mono | 10px | 700 | 0.20em |
| Nav / Meta | Space Mono | 11–12px | 400 | 0.04–0.10em |
| How-item heading | Space Grotesk (uppercase) | 11px | 700 | 0.08em |
| Counter (01/02/03) | Space Mono | 10px | 700 | 0.10em |

---

## Spacing & Radius

- **Border-radius:** 0px everywhere. Non-negotiable.
- **Section padding:** 64px top/bottom, 64px left (scales to 80px at ≥1400px, 24px on mobile).
- **Sidebar width:** 220px fixed, sticky, full-height.
- **Hairline:** 1px solid `#222` — sections, sidebar border, grid splits.
- **Elnath accent:** `border-left: 3px solid #d4ff00` — the only decorative line wider than 1px.

---

## Do / Don't

**Do**
- Use `--acid` only for the sphere SVG stroke, the Elnath left-border, and the footer dot.
- Keep all section labels in Space Mono UPPERCASE at 0.20em tracking.
- Apply negative letter-spacing (-0.02 to -0.03em) to every display headline.
- Let content columns be wide on desktop — no narrow centered column on a 1440px screen.

**Don't**
- Add border-radius to anything.
- Use `--acid` as a text color, button fill, or hover state anywhere.
- Add shadows, gradients, glows, or background fills beyond `--black` and `--surface`.
- Introduce a third typeface or a third weight (only 400 / 500 / 700 are in use).

---

## Iteration Guide

Tighten by removing — cut padding before adding any element; if a section feels weak, increase the headline tracking gap or drop the body color one step darker.

---

## Known Gaps

- No `:hover` animation on nav links — could add a 1px `border-bottom: 1px solid #444` on hover for tactility without breaking the aesthetic.
- Mobile sidebar collapses to a top bar; the brand mark loses vertical breathing room at 320px — min-width guard may be needed.
- Pull-question section has no section-label eyebrow — intentional (it reads as a standalone statement), but may feel inconsistent next to labeled sections.
- No favicon variant for dark contexts — existing `favicon.svg` may need a `--acid` stroke version.
