# Esfera Research — "Technical Instrument" Design Spec

## North-Star Signature

A lab dashboard, not a marketing page. Dark canvas, surface-ladder depth, and one restrained accent — cold electric lime (#9eff00) used only to signal live state and the brand mark. Everything else is controlled, quiet, exact. The vibe: you opened a terminal that has good taste.

---

## Accent choice: Cold Electric Lime

**White-as-action was rejected** — too many dark sites do Raycast-style white-on-black CTA buttons. Lime (#9eff00) is rarer, reads as "active / live / signal" without the AI-cliché purple/cyan. It appears in exactly three places: the globe mark stroke, the status dot, and the pull-quote left border + italics. Everywhere else is neutral.

---

## Color Tokens

| Token | Hex | Role |
|---|---|---|
| `--canvas` | `#08090a` | Page background (true almost-black) |
| `--s1` | `#0e0f11` | Surface level 1 — rail, cards, pulled blocks |
| `--s2` | `#141517` | Surface level 2 — hover state, code blocks |
| `--s3` | `#1a1c1f` | Surface level 3 (reserved for nested depth) |
| `--border` | `#1d1f22` | Default hairline border |
| `--border-hi` | `#2a2d31` | Hover / emphasis border |
| `--t-primary` | `#e8eaed` | Headings, strong text |
| `--t-secondary` | `#8a9099` | Body, paragraph text |
| `--t-muted` | `#4d5260` | Labels, eyebrows, meta |
| `--accent` | `#9eff00` | Brand mark, live dot, pull-quote accent (lime) |
| `--accent-dim` | `rgba(158,255,0,0.12)` | Accent fill on status badge / tag bg |

**Elevation rule**: depth is conveyed by surface value alone. No drop shadows, ever.

---

## Type Tokens

| Role | Family | Size | Weight | Tracking |
|---|---|---|---|---|
| Display (h1) | Inter | clamp(28px–44px) | 600 | -0.04em |
| Section h2 | Inter | 13px | 600 | -0.02em |
| Body / lede | Inter | 14–16px | 400 | normal |
| Pull quote | Inter | 17px | 400 | -0.015em |
| Eyebrow / label | JetBrains Mono | 9–10px | 500 | +0.12–0.15em, UPPERCASE |
| Nav / meta | JetBrains Mono | 10–11px | 400–500 | +0.08–0.1em |
| Code quote | JetBrains Mono | 11px | 400 | normal |

`font-feature-settings: 'cv05' 1, 'ss01' 1` applied to body and h1 for Inter's alternate digits and straight-sided 'a'.

---

## Spacing & Radius

- **Base unit**: 4px. Scale: 4 / 8 / 12 / 16 / 20 / 24 / 32 / 40 / 48 / 64 / 80px.
- **Section rhythm**: 48px between major sections (`.section-div` + margin pattern).
- **Border radius**: `--r-sm: 4px` (badges, small insets), `--r-md: 6px` (cards, blocks).
- **Rail width**: 220px fixed on ≥860px viewport; collapses to full-width topbar below.

---

## Do / Don't

**Do**
1. Use surface ladder (#08090a → #0e0f11 → #141517) to create depth — never shadows.
2. Keep lime accent to signals only: mark, live status, single left border on the pull-quote.
3. Use JetBrains Mono UPPERCASE + wide tracking for ALL section eyebrows and meta labels.
4. Let hairline borders (1px `#1d1f22`) do the heavy lifting for structure.

**Don't**
1. Don't add drop shadows, glows, or blur effects — none, anywhere.
2. Don't use purple, cyan, or any "AI gradient" as accent — this direction owns lime.
3. Don't stretch the content column to full width on wide viewports; cap at 760px for readability.
4. Don't use rounded corners larger than 6px — this is precision instrument chrome, not a consumer app.

---

## Iteration Guide

Swap the accent from lime to `#c8ff80` (softer) or `#ffffff` (white-as-action) to test a cooler, more minimal read — the rest of the system needs no changes.

---

## Known Gaps

- No actual favicon SVG included (references `../../favicon.svg` from parent; add a lime-stroked version for this direction).
- The `한국어` toggle links to `#` — wire to `/ko/` when the Korean page exists.
- Principle cards collapse to single-column on mobile, which is correct but makes the 2×3 grid very long — consider an accordion for phone sizes in a future pass.
- No `:focus-visible` ring styles defined — add `outline: 2px solid var(--accent); outline-offset: 2px` on interactive elements for keyboard accessibility.
