# Design blend-warm — Warm Serif Blend (F base + one E move)

## North-Star Signature

F's calm paper-journal warmth as the dominant register — generous leading, Newsreader body, oxblood used like a wax seal — with exactly one bold move borrowed from E: the hero H1 at Fraunces `opsz 144`, `weight 700`. That single headline carries E's engraved thick/thin drama while everything else remains unhurried. The page reads warm first, present second.

---

## Color Tokens

| Token         | Light                     | Dark                       | Use                              |
|---------------|---------------------------|----------------------------|----------------------------------|
| `--bg`        | `#f6f1e8` warm amber paper | `#181410` warm near-black  | Page background                  |
| `--bg-alt`    | `#efe9db`                 | `#1f1b17`                  | Elnath block fill                |
| `--surface`   | `#f9f5ef`                 | `#231f1b`                  | Reserved for future cards        |
| `--ink`       | `#2a241d` warm brown-black | `#ede6da` warm cream       | Primary text, headings           |
| `--ink-muted` | `#6b5f52`                 | `#a49a8e`                  | Section labels, nav              |
| `--ink-faint` | `#b0a598`                 | `#4a4440`                  | Meta, stamps, lang toggle        |
| `--accent`    | `#7c3a2c` oxblood         | `#b85c47` warm terracotta  | Mark, pull-quote border, em text, period, dot |
| `--rule`      | `#d9d0c3`                 | `#302a24`                  | Hairlines, list dividers         |

**Accent budget:** sphere mark stroke, H1 period, pull-quote left border, `.studying` dashes, `em` in Elnath, footer dot. Seven uses maximum. Never as a fill or background.

---

## Type Tokens

| Role              | Font                  | Weight / Style          | Size / Treatment                          |
|-------------------|-----------------------|-------------------------|-------------------------------------------|
| Hero display      | Fraunces, opsz 144    | 700 (E's bold move)     | `clamp(3rem, 8vw, 6.5rem)`, lh 1.05, ls −0.025em |
| Pull-quote        | Fraunces, opsz auto   | 300i italic             | `clamp(1.2rem, 2.5vw, 1.6rem)`, lh 1.5   |
| Day-zero head     | Fraunces, opsz auto   | 400i italic             | `clamp(1.4rem, 3vw, 2.1rem)`, lh 1.25    |
| Section labels    | Fraunces, opsz auto   | 500, UPPERCASE          | `0.7rem`, ls `0.17em`                     |
| Lede              | Newsreader, opsz auto | 400                     | `clamp(1.08rem, 2vw, 1.22rem)`, lh 1.68  |
| Body              | Newsreader, opsz auto | 400                     | `1rem`, lh 1.78                           |
| Meta / nav / sig  | IBM Plex Mono         | 400–500, UPPERCASE      | `0.59–0.61rem`, ls `0.07–0.09em`         |

---

## Spacing & Radius

- **Section gap (`--gap`):** `clamp(2.8rem, 5vw, 3.8rem)` — calm, unhurried rhythm
- **Main padding:** 5.5rem top / `clamp(2rem, 6vw, 5.5rem)` sides (wide: 6.5rem top / 8vw side)
- **Column measure:** body max 62ch; pull-quote max 54ch; lede max 60ch
- **Rail:** sticky 220px (256px at 1400px+), 2.5rem padding, 1px border-right
- **Elnath block:** `--bg-alt` fill + 1.5px accent top border only — no radius, no shadow
- **Radius: 0 everywhere.** Focus ring gets `border-radius: 1px` as sole exception.
- **No shadows. No gradients** except the single radial warm vignette on `body`.

---

## 4 Do

1. Let the hero breathe. The `opsz 144` Fraunces H1 at weight 700 is the one loud move — give it vertical room before the lede.
2. Use oxblood like a wax seal: one or two places per screen section, never repeated in a row.
3. Keep Newsreader body at 1rem / lh 1.78 — the warmth lives in the leading, not the size.
4. Honor the 62ch measure. At wide viewports, add whitespace to the right, never wider text.

## 4 Don't

1. Don't raise the hero weight above 700 or add a second opsz-144 element — the boldness is effective only because it's singular.
2. Don't use accent as a background or fill — oxblood is a stroke, border, and text color only.
3. Don't add shadows, heavy gradients, border-radius cards, or glowing elements.
4. Don't replace Newsreader body with Fraunces — the contrast between display and body is the whole flavor.

---

## Iteration Guide

To push warmer: shift `--bg` toward `#f2ead8` and `--accent` toward `#8c4030`. To pull back the bold-move: reduce hero weight to 500 and cap clamp at `5rem` — you get a more purely-F result. To add a second textural layer: try Fraunces smallcaps (`font-variant-caps: small-caps`) on the pull-quote attribution only.

---

## Known Gaps

- **Dark-mode vignette:** the `body` `background-image` radial gradient is light-mode tuned; in dark mode it may be too subtle to notice — consider increasing opacity to `0.065` for dark.
- **Korean toggle** links to `href="#"` (placeholder); implement as `/ko/` when translation exists.
- **Fraunces opsz 144 download weight:** the variable font range 9–144 is a large file; add `font-display: swap` via a `@font-face` override if FOUT is observed on slow connections.
- **Day-zero heading** uses `role="heading" aria-level="2"` on a `<p>` tag — refactor to `<h2 class="day-zero-head">` when the label-vs-display h2 styles are reconciled.
