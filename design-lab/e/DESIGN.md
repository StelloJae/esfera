# Direction E — Bold Serif Design Spec

## North-Star Signature

A warm, editorial research house: Anthropic's calm serif gravity scaled up and made bolder, but with Esfera's confrontational voice and oxblood edge. The signature move is **large-scale Fraunces at optical size 144** for the hero (ultra-high contrast thick/thin strokes) paired with **IBM Plex Mono uppercase labels** as section eyebrows — that serif-display + monospaced-uppercase combination is the Anthropic-evoking hallmark. One accent color, used sparingly: oxblood in light mode, warm clay in dark.

---

## Color Tokens

| Token        | Light          | Dark           | Use                        |
|--------------|----------------|----------------|----------------------------|
| `--bg`       | `#f4efe6`      | `#16130f`      | Page background            |
| `--surface`  | `#eee8db`      | `#1d1a14`      | Card / Elnath block        |
| `--ink`      | `#1c1813`      | `#ede6d8`      | Primary text               |
| `--ink-mid`  | `#4a4035`      | `#b5a596`      | Body / secondary text      |
| `--ink-faint`| `#8a7a6e`      | `#6a5a4e`      | Labels, meta, stamps       |
| `--accent`   | `#7a1f12`      | `#b06a2c`      | Mark, period, rules, em    |
| `--rule`     | `#d4c9b8`      | `#2c2820`      | Hairlines, borders         |

**The accent is oxblood (`#7a1f12`) in light mode** — not Anthropic's coral `#cc785c`. In dark mode it shifts to warm clay `#b06a2c` for legibility. One accent, rationed to: the sphere mark, the hero period, the 3px pull-quote top rule, the Elnath card left border, and emphasis spans.

---

## Type Tokens

| Role            | Family                  | Weight | opsz / variant          | Size                        | Tracking      |
|-----------------|-------------------------|--------|-------------------------|-----------------------------|---------------|
| Hero display    | Fraunces                | 900    | opsz 144, SOFT 0        | `clamp(3.25rem, 8.5vw, 7rem)` | `−0.03em`   |
| Pull quote      | Fraunces italic         | 400    | opsz 72                 | `clamp(1.2rem, 2.4vw, 1.7rem)` | default    |
| Section display | Fraunces                | 700    | opsz 72                 | `clamp(1.5rem, 3.2vw, 2.5rem)` | `−0.02em`  |
| Section label   | IBM Plex Mono           | 500    | —                       | `0.75rem`                   | `+0.18em`, UPPERCASE |
| Eyebrow         | IBM Plex Mono           | 400    | —                       | `0.75rem`                   | `+0.16em`, UPPERCASE |
| Body            | Fraunces                | 300–400| opsz auto               | `1.0625rem`                 | default       |
| Rail nav        | Fraunces italic         | 300    | —                       | `0.9375rem`                 | default       |
| Meta / stamp    | IBM Plex Mono           | 400    | —                       | `0.6875–0.75rem`            | `+0.08–0.12em` |

**Key technique:** Fraunces's `opsz` axis. At `144` the thick/thin stroke contrast is extreme — this is the "engraved" quality that reads as confident editorial, not tech.

---

## Spacing & Radius

- `--pad`: `clamp(1.75rem, 5vw, 4rem)` — main content horizontal padding
- `--gap`: `clamp(3rem, 7vw, 5.5rem)` — between sections
- Sidebar width: `216px` fixed
- **Border radius: 0 everywhere.** No pill, no card softening.
- **No shadows.** Depth via border + surface color contrast only.

---

## Do / Don't

**Do**
1. Use Fraunces at `opsz 144` for the hero — the thick/thin contrast is the whole mood.
2. Keep the accent to 5–6 places maximum. Every new use dilutes it.
3. Use mono uppercase labels (`IBM Plex Mono`, `letter-spacing: 0.18em`) for all section eyebrows — this is the Anthropic-evoking signature.
4. Let the grid breathe: large `--gap` between sections, never compressed.

**Don't**
1. Don't add border-radius. Squared corners are load-bearing to the "serious research house" feel.
2. Don't use accent on body text or nav links. Reserve it for structural moments only.
3. Don't add a second accent color. The whole system works because there's only one warm signal.
4. Don't introduce shadows, gradients, or glows. These collapse the calm editorial gravity immediately.

---

## How It Differs from Anthropic

| Dimension       | Anthropic                          | Direction E (Esfera)                    |
|-----------------|------------------------------------|-----------------------------------------|
| Accent          | Coral `#cc785c`                    | Oxblood `#7a1f12` / clay `#b06a2c`     |
| Background      | Exact warm cream `#faf5eb` range   | Bone `#f4efe6` / near-black `#16130f`  |
| Hero scale      | Large but measured                 | More aggressive — `clamp` to `7rem`    |
| Voice           | Calm, institutional                | Confrontational, self-critical          |
| Structure       | Full-bleed horizontal layouts      | Sidebar rail + columnar main            |
| Mark            | Anthropic's own mark               | Esfera engraved sphere (3-line globe)  |

**Read as:** inspired by Anthropic's editorial serif calm; differentiated by bolder scale, a darker accent, a confrontational voice, and the sidebar-rail layout Anthropic doesn't use.

---

## Iteration Guide

To increase boldness: raise hero `font-weight` to `900` and reduce `line-height` toward `0.95`. To warm up further: deepen `--bg` slightly toward `#ede8de`. To add a second typographic texture: introduce Fraunces small-caps for pull-quote attribution only.

---

## Known Gaps

- **No dark/light toggle control** — relies on `prefers-color-scheme` only; a manual toggle could be added as a single `<button>` with a `data-theme` attribute on `<html>`.
- **Fraunces variable axes** (`SOFT`, `WONK`) are set but may be ignored in older WebKit; fallback to Georgia is acceptable.
- **No hover states on cards** — intentional (no interaction on static content), but the Elnath card could gain a subtle left-border glow on hover if needed.
- **Mobile rail** collapses to a top bar cleanly, but nav links at `< 360px` may need `font-size` reduction.
