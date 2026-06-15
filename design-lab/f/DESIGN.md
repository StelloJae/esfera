# Design F — Warm Serif (Anthropic-Inspired)

## North-Star Signature

A warm scholarly journal that happens to run on AI. Large-uppercase serif headings
create editorial gravity; oxblood accent marks presence without shouting. The page
breathes — generous spacing, classic measure, paper warmth. Refined and inviting,
not loud.

---

## Color Tokens

| Token         | Light (`#f6f1e8` base) | Dark (`#181410` base)  |
|---------------|------------------------|------------------------|
| `--bg`        | `#f6f1e8` warm paper   | `#181410` warm near-black |
| `--bg-alt`    | `#efe9db`              | `#1f1b17`              |
| `--surface`   | `#f9f5ef`              | `#231f1b`              |
| `--ink`       | `#2a241d` warm brown-black | `#ede6da` warm cream |
| `--ink-muted` | `#6b5f52`              | `#a49a8e`              |
| `--ink-faint` | `#b0a598`              | `#4a4440`              |
| `--accent`    | `#7c3a2c` oxblood      | `#b85c47` warm terracotta |
| `--rule`      | `#d9d0c3`              | `#302a24`              |

**Warm accent: Oxblood (`#7c3a2c`)**. Not Anthropic coral (#cc785c) — deeper,
more wine-dark; used only on: sphere mark, pull-quote border, em text, dash glyphs,
the footer dot. Never as a fill or background.

---

## Type Tokens

| Role             | Font                   | Weight / Style        | Size / Treatment         |
|------------------|------------------------|-----------------------|--------------------------|
| Display headline | Fraunces (opsz auto)   | 300 — light           | clamp(2.4rem → 3.8rem), lh 1.1 |
| Section labels   | Fraunces               | 500, uppercase        | 0.72rem, ls 0.16em — editorial signature |
| Pull quote       | Fraunces italic        | 300i                  | clamp(1.25rem → 1.65rem) |
| Lede             | Newsreader             | 400                   | clamp(1.08rem → 1.22rem) |
| Body             | Newsreader             | 400                   | 1rem, lh 1.78            |
| Meta / nav / sig | IBM Plex Mono          | 400–500               | 0.60–0.62rem, uppercase  |

---

## Spacing & Radius

- **Column measure:** max 62ch body, 54ch pull-quote — classic editorial
- **Main padding:** 5.5rem top, generous side gutters (5–6vw)
- **Section gap:** h2 margin-top 3.4rem — calm, unhurried
- **Rail:** sticky 220px, 2.5rem padding, single 1px border-right rule
- **Elnath block:** bg-alt fill, 1.5px accent top-border only — no radius, no shadow
- **Radius:** zero throughout — no pill shapes, no rounded cards

---

## 4 Do

1. **Let the serif breathe.** Large Fraunces at light weight with generous leading.
   Never crowd the headings.
2. **Use oxblood sparingly.** Mark, left-border of pull-quote, em highlights, footer
   dot — that's it. One accent, used like a wax seal, not a highlighter.
3. **Honor the measure.** Keep body copy at 62ch. Wide viewports add whitespace,
   not wider text blocks.
4. **Monospace for metadata only.** Nav, sig line, brand name — the Plex Mono
   grounds the page without competing with Fraunces.

## 4 Don't

1. **No shadows or gradients** (the single radial vignette on `body` is the limit).
2. **No radius** on any element — not on the Elnath block, not on nav links.
3. **No accent fills** — oxblood is a stroke / border / text color only; never a
   background or button fill.
4. **No AI visual clichés** — no glowing nodes, no purple/cyan, no network art,
   no stock imagery.

---

## Iteration Guide

Adjust warmth by shifting `--bg` toward amber (`#f2e9d5`) or back toward neutral
(`#f0ece4`); accent can move from oxblood toward warm clay (`#8c5a40`) depending
on mood — keep ΔE between light/dark accent < 15 for consistency.

---

## Known Gaps

- **Favicon / og:image** not wired (paths relative to `/Users/stello/esfera/` root).
- **Font loading on slow connections:** Fraunces opsz range is large; add
  `font-display: swap` override if FOUT is observed.
- **Korean translation** (`/ko/`) not implemented; toggle links to `href="ko/"`.
- **Pull-quote on mobile (< 380px):** padding-left 1.4rem may feel tight;
  consider reducing to 1rem at that breakpoint.

---

## How F differs from Anthropic & from sibling E

**vs Anthropic:** Oxblood replaces Anthropic coral. Warm brown-black ink (`#2a241d`)
replaces near-neutral charcoal. Esfera's voice is edgier and more declarative.
The sphere mark replaces any Anthropic logoform.

**vs sibling E:** F turns UP paper warmth (amber-shifted bg, oxblood accent vs E's
harder ink choice) and turns DOWN display scale (smaller clamp ceiling, lighter
weight). Section labels stay uppercase Fraunces — the shared DNA — but F's overall
contrast is softer and spacing more generous. E is bolder; F is the warm reading
lamp in the corner.
