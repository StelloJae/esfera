# Blend-Mid — Balanced Midpoint Design Spec

## North-Star Signature

Editorial research house at a confident, readable scale. E's structural rail + serif confidence; F's warm palette, Newsreader body text, and generous breath. The hero Fraunces runs at `opsz 72` (not E's aggressive `144`), weight `700` (not F's whisper `300`) — high-contrast but unhurried. IBM Plex Mono uppercase labels preserve the Anthropic-evoking signature shared by both parents. One accent — warm oxblood — used like punctuation.

---

## Color Tokens

| Token         | Light           | Dark            | Use                            |
|---------------|-----------------|-----------------|--------------------------------|
| `--bg`        | `#f6f1e8`       | `#181410`       | Page background (F's palette)  |
| `--bg-alt`    | `#efe9db`       | `#1f1b17`       | Elnath card fill               |
| `--surface`   | `#f9f5ef`       | `#231f1b`       | Reserved surface               |
| `--ink`       | `#2a241d`       | `#ede6da`       | Primary text                   |
| `--ink-mid`   | `#6b5f52`       | `#a49a8e`       | Body, secondary text           |
| `--ink-faint` | `#b0a598`       | `#4a4440`       | Labels, meta, stamps           |
| `--accent`    | `#7c3a2c`       | `#b85c47`       | Mark, period, borders, em      |
| `--rule`      | `#d9d0c3`       | `#302a24`       | Hairlines, card borders        |

**Accent family: warm oxblood `#7c3a2c` (light) / terracotta `#b85c47` (dark).** Not E's cooler `#7a1f12`, not Anthropic's coral. Used only on: sphere mark, hero period, pull-quote left border, Elnath card top border, emphasis text, footer dot.

---

## Type Tokens

| Role             | Font                   | Weight | opsz / variant | Size                          | Tracking       |
|------------------|------------------------|--------|----------------|-------------------------------|----------------|
| Hero display     | Fraunces               | 700    | opsz 72        | `clamp(2.8rem, 6.5vw, 5rem)` | `−0.025em`     |
| Pull quote       | Fraunces italic        | 300    | opsz 72        | `clamp(1.2rem, 2.4vw, 1.65rem)` | default     |
| Section display  | Fraunces               | 600    | opsz 48        | `clamp(1.35rem, 2.8vw, 2.1rem)` | `−0.018em`  |
| Section label    | IBM Plex Mono          | 500    | —              | `0.68rem`                     | `+0.16em`, UPPERCASE |
| Eyebrow          | IBM Plex Mono          | 400    | —              | `0.68rem`                     | `+0.14em`, UPPERCASE |
| Body             | Newsreader             | 400    | opsz auto      | `1rem`                        | default        |
| Lede             | Newsreader             | 400    | —              | `clamp(1rem, 1.9vw, 1.18rem)` | default        |
| Rail nav         | Fraunces italic        | 300    | opsz 36        | `0.875rem`                    | default        |
| Meta / stamp     | IBM Plex Mono          | 400–500| —              | `0.6–0.68rem`                 | `+0.08–0.1em`  |

---

## Spacing & Radius

- `--pad-h`: `clamp(2rem, 5.5vw, 5rem)` — main horizontal padding
- `--pad-v`: `clamp(3.5rem, 7vw, 5.5rem)` — main vertical top padding
- `--gap`: `clamp(2.8rem, 5.5vw, 4.5rem)` — between sections
- Rail: sticky `224px`, single `1px border-right`
- Body measure: `max-width: 62ch` (pull-quote `54ch`)
- **Border radius: zero everywhere.** No pill shapes, no card softening.
- **No shadows, no gradients.** Depth via surface color and ruled borders only.

---

## 4 Do

1. **Moderate the hero.** `opsz 72` + weight `700` reads confident without E's aggressive extremes — keep it there.
2. **Let Newsreader carry the body.** Its optical warmth at `1rem/1.78` is the reading comfort that distinguishes this from E.
3. **IBM Plex Mono uppercase for all labels.** The mono+caps combination is the shared editorial signature — preserve it.
4. **Use the accent like a wax seal.** Mark, period, pull-quote border, card top-rule, footer dot — nothing more.

## 4 Don't

1. **Don't push opsz beyond 72 on this build.** `opsz 144` tips into E's territory; stay mid.
2. **Don't add radius.** Squared corners are structural to the "serious research house" register.
3. **Don't swap Newsreader back to Fraunces for body text.** The warmth difference is real; Fraunces body pulls too close to E.
4. **Don't add shadows or gradients.** Any vignette or box-shadow collapses the editorial calm immediately.

---

## Iteration Guide

To tilt toward E: raise hero weight to `900`, set `opsz 144`, narrow `--gap`. To tilt toward F: lower hero weight to `400`, reduce max clamp to `3.8rem`, widen body measure to `66ch`.

---

## Known Gaps

- No manual light/dark toggle — relies on `prefers-color-scheme` only.
- Korean (`/ko/`) toggle links to `href="#"` (placeholder).
- Principles rendered as a ruled single-column list rather than E's 2-column grid — revisit at wider viewports if density is desired.
- `font-display: swap` not set on Google Fonts URL; add `&display=swap` override if FOUT is observed on slow connections.
