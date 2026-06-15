# Blend-Bold — Design Spec

## Signature

**E's confidence, F's warmth.** Fraunces at `opsz 144 / weight 900` for the hero — the extreme thick/thin stroke contrast that reads as engraved editorial authority — but sitting on F's warm paper palette (`#f6f1e8`) with F's Newsreader body and F's oxblood accent family. The sidebar rail is E's (structural, sticky, narrow); the reading experience is F's (calm, generous, Newsreader-set body). IBM Plex Mono uppercase labels tie both worlds together.

---

## Color Tokens

| Token         | Light                   | Dark                    | Use                          |
|---------------|-------------------------|-------------------------|------------------------------|
| `--bg`        | `#f6f1e8` warm paper    | `#181410` warm near-black | Page background              |
| `--bg-alt`    | `#efe9db`               | `#1f1b17`               | Elnath card fill             |
| `--surface`   | `#f9f5ef`               | `#231f1b`               | Subtle surface (reserved)    |
| `--ink`       | `#2a241d` warm brown    | `#ede6da` warm cream    | Primary text                 |
| `--ink-mid`   | `#6b5f52`               | `#a49a8e`               | Lede, body prose             |
| `--ink-faint` | `#b0a598`               | `#4a4440`               | Labels, meta, stamps         |
| `--accent`    | `#7c3a2c` oxblood       | `#b85c47` terracotta    | Mark, period, rules, em      |
| `--rule`      | `#d9d0c3`               | `#302a24`               | Hairlines, grid borders      |

**Accent family is F's** (`#7c3a2c`/`#b85c47`), not E's cooler oxblood (`#7a1f12`/`#b06a2c`). Warmer, slightly more terracotta in dark. One accent; used only on: sphere mark, hero period, pull-quote 3px top-rule, Elnath card left+top border, em highlights, footer dot.

---

## Type Tokens

| Role             | Family          | Weight / Style        | opsz  | Size                          | Tracking     |
|------------------|-----------------|-----------------------|-------|-------------------------------|--------------|
| Hero display     | Fraunces        | 900                   | 144   | `clamp(3.4rem, 9vw, 7.25rem)` | `−0.03em`    |
| Section display  | Fraunces        | 700                   | 72    | `clamp(1.5rem, 3.2vw, 2.5rem)` | `−0.02em`   |
| Pull quote       | Fraunces italic | 300i                  | 72    | `clamp(1.25rem, 2.6vw, 1.75rem)` | default   |
| Section label    | IBM Plex Mono   | 500                   | —     | `0.72rem`                     | `+0.18em`, UPPERCASE |
| Eyebrow          | IBM Plex Mono   | 500                   | —     | `0.72rem`                     | `+0.18em`, UPPERCASE |
| Lede             | Newsreader      | 400                   | —     | `clamp(1.05rem, 1.9vw, 1.2rem)` | default   |
| Body             | Newsreader      | 400                   | —     | `1rem`, lh `1.78`             | default      |
| Rail nav         | Fraunces italic | 300i                  | —     | `0.9375rem`                   | default      |
| Meta / sig       | IBM Plex Mono   | 400–500               | —     | `0.6–0.72rem`                 | `+0.08–0.12em`, UPPERCASE |

---

## Spacing & Radius

- `--pad`: `clamp(2rem, 5.5vw, 4.5rem)` — main horizontal padding
- `--gap`: `clamp(3rem, 7vw, 5.5rem)` — between major sections
- Rail: `220px` fixed, sticky, single 1px right border
- Body measure: `62ch` max; pull-quote `54ch`; lede `58ch`
- **Radius: 0 everywhere.** No softening on cards or any element.
- **No shadows.** Depth via border color + `--bg-alt` fill only.

---

## 4 Do

1. **Hero at opsz 144, weight 900.** The extreme thick/thin contrast is the defining move — do not reduce weight or opsz.
2. **All section eyebrows as IBM Plex Mono uppercase.** `letter-spacing: 0.18em` — this is the Anthropic-evoking shared DNA of E and F.
3. **One accent, rationed to ~6 structural moments.** Mark, period, pull-quote top-rule, card border, em text, footer dot. Every new use dilutes it.
4. **Newsreader for all prose.** The shift from display Fraunces to humanist Newsreader body is what creates reading comfort despite the bold display — don't mix them up.

## 4 Don't

1. **No border-radius anywhere.** Squared corners are load-bearing to the research-house gravity.
2. **No shadows, gradients, or glows.** The single-direction border and bg-alt surface is the entire depth system.
3. **No accent on nav links or body text.** Reserve it for structural moments; hover states use `--ink-mid`.
4. **No AI visual clichés.** No purple/cyan, no node art, no glowing orbs — the sphere mark is enough.

---

## Iteration Guide

To push bolder: increase hero `clamp` ceiling toward `8rem`, tighten `letter-spacing` to `−0.04em`. To warm up further: shift `--bg` toward `#f2ead8`. To soften: drop hero weight to `700` and increase pull-quote `opsz` toward `144`. Accent can travel toward terracotta (`#8c4a38`) without breaking the system — keep light/dark ΔE < 15.

---

## Known Gaps

- **No manual dark/light toggle** — relies on `prefers-color-scheme` only; add `data-theme` on `<html>` + one `<button>` to enable.
- **Korean translation** (`/ko/`) not implemented; lang toggle links to `href="#"`.
- **Fraunces `SOFT`/`WONK` axes** not set (optional); older WebKit falls back to Georgia cleanly.
- **Pull-quote on mobile (< 380px):** the 3px top border may feel disconnected at very narrow widths; consider adding `padding-left: 0.75rem` and a left-border fallback.
