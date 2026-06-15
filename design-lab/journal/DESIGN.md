# DESIGN.md — Esfera Research · Editorial Academic Print

## North Star
A beautifully typeset research journal that earns trust through editorial restraint: every design decision signals *this lab publishes*, not this lab ships product.

---

## Color Tokens

| Token | Light | Dark |
|---|---|---|
| `--paper` | `#f6f2e9` (warm parchment) | `#14120f` (near-black) |
| `--ink` | `#1a1714` (rich ink) | `#ede8db` (warm cream) |
| `--ink-mid` | `#4a443d` (mid tone) | `#b5ad9e` |
| `--ink-faint` | `#9a9188` (captions/meta) | `#6a6156` |
| `--accent` | `#7a1f12` (oxblood) | `#c04030` (lighter oxblood) |
| `--rule` | `#d4ccbb` (hairline rule) | `#2e2a24` |
| `--surface` | `#ede9df` (Elnath tinted bg) | `#1d1a16` |

Switched via `@media (prefers-color-scheme: dark)`.

---

## Type Tokens

| Role | Family | Size | Weight | Tracking |
|---|---|---|---|---|
| Display / H1 | Fraunces (`opsz: auto`) | `clamp(2.6rem, 5.5vw, 4rem)` | 300 | `-0.02em` |
| Pull quote | Fraunces italic | `clamp(1.3rem, 2.5vw, 1.55rem)` | 300 | `-0.01em` |
| Eyebrow / Section labels | IBM Plex Mono | `0.68rem` | 500 | `+0.12em` (uppercase) |
| Nav / Meta | IBM Plex Mono | `0.68–0.72rem` | 400/500 | `+0.04–0.08em` |
| Body / Lede | Fraunces | `1rem / 1.05rem` | 400 | normal |
| Elnath block H3 | Fraunces italic | `1.35rem` | 400 | `-0.01em` |

Leading: `1.72–1.78` for body; `1.1` for headline; `1.45` for pull quote.
Measure: body capped at `68ch`; principles grid at `90ch`.

Drop cap: `.lede::first-letter` — 3.6em Fraunces, oxblood, floated left.

---

## Spacing & Radius

- Section spacing: `3.2rem` above section breaks
- Rail padding: `2.4rem 1.6rem 2rem 2rem` (desktop sticky)
- Elnath block: `1.8rem 2rem` padding, `2px solid accent` top border
- Principles grid: `1.2rem 1.4rem` per cell, ruled grid (1px borders on all sides)
- Rules / hairlines: `1px solid var(--rule)` — no border-radius on rules or ruled grids
- Radius: none — this is a flat print aesthetic

---

## Do / Don't

**Do**
1. Use thin rules (1px, `--rule`) to divide sections — let whitespace and type hierarchy do the work.
2. Keep the accent (oxblood) isolated: drop cap, pull-quote bar, eyebrow text, Elnath top border, footer dot only.
3. Let Fraunces optical sizing shift the display weight subtly — keep `font-optical-sizing: auto`.
4. Use IBM Plex Mono at small sizes with wide tracking for all metadata, labels, and nav — the mono/serif contrast is the identity.

**Don't**
1. Don't add color fills to the studying list or body copy — the accent must remain sparse.
2. Don't increase border-radius anywhere; all containers are flat-cornered (printed-page feel).
3. Don't add gradients, shadows, or glows. The tinted `--surface` block is the only fill beyond paper.
4. Don't let the rail grow — it's a margin column, not a sidebar dashboard.

---

## Iteration Guide

To shift warmer/cooler: adjust `--paper` hue (more yellow = warmer, more gray = cooler) and mirror `--surface` to be ±5% darker. The accent follows independently.

---

## Known Gaps

- Korean (`한국어`) typography not tested — Fraunces covers Latin only; a CJK fallback stack should be added when building the `/ko/` page.
- The sticky rail collapses to a horizontal nav bar on mobile/tablet — nav ordering and the `lang` toggle placement could be refined for very narrow viewports (< 360px).
- `font-optical-sizing: auto` requires Chrome 99+ / Safari 15.4+; older browsers fall back to default optical size (acceptable, not broken).
