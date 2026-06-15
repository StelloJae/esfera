# Design fluid-warm — Warm Serif Blend, Fluid Scaling

## North-Star Signature

F's calm paper-journal warmth as the dominant register — generous leading, Newsreader body, oxblood used like a wax seal — with exactly one bold move borrowed from E: the hero H1 at Fraunces `opsz 144`, `weight 700`. That single headline carries E's engraved thick/thin drama while everything else remains unhurried. The page reads warm first, present second.

The responsive system is fluid (Hermes-style): the root font-size scales with viewport width via `clamp()`, so every rem-sized dimension — type, spacing, the rail, the shell — grows proportionally as the window widens. No breakpoint jumps. No dead side margins. One collapse to a top-bar at narrow widths.

---

## Color Tokens

| Token         | Light                      | Dark                       | Use                              |
|---------------|----------------------------|----------------------------|----------------------------------|
| `--bg`        | `#f6f1e8` warm amber paper | `#181410` warm near-black  | Page background                  |
| `--bg-alt`    | `#efe9db`                  | `#1f1b17`                  | Elnath block fill                |
| `--surface`   | `#f9f5ef`                  | `#231f1b`                  | Reserved for future cards        |
| `--ink`       | `#2a241d` warm brown-black | `#ede6da` warm cream       | Primary text, headings           |
| `--ink-muted` | `#6b5f52`                  | `#a49a8e`                  | Section labels, nav              |
| `--ink-faint` | `#b0a598`                  | `#4a4440`                  | Meta, stamps, lang toggle        |
| `--accent`    | `#7c3a2c` oxblood          | `#b85c47` warm terracotta  | Mark, pull-quote border, em text, period, dot |
| `--rule`      | `#d9d0c3`                  | `#302a24`                  | Hairlines, list dividers         |

**Accent budget:** sphere mark stroke, H1 period, pull-quote left border, `.studying` dashes, `em` in Elnath, footer dot. Seven uses maximum. Never as a fill or background.

---

## Type Tokens

| Role              | Font                  | Weight / Style          | Size / Treatment                                    |
|-------------------|-----------------------|-------------------------|-----------------------------------------------------|
| Hero display      | Fraunces, opsz 144    | 700 (E's bold move)     | `clamp(2.8rem, 6.2vw, 7.5rem)`, lh 1.05, ls −0.025em |
| Pull-quote        | Fraunces, opsz auto   | 300i italic             | `clamp(1.2rem, 2.2vw, 2rem)`, lh 1.5               |
| Day-zero head     | Fraunces, opsz auto   | 400i italic             | `clamp(1.4rem, 3vw, 2.1rem)`, lh 1.25              |
| Section labels    | IBM Plex Mono         | 500, UPPERCASE          | `0.68rem`, ls `0.16em`                              |
| Lede              | Newsreader, opsz auto | 400                     | `clamp(1rem, 1.7vw, 1.2rem)`, lh 1.68              |
| Body              | Newsreader, opsz auto | 400                     | `1rem`, lh 1.78                                     |
| Meta / nav / sig  | IBM Plex Mono         | 400–500, UPPERCASE      | `0.59–0.62rem`, ls `0.07–0.1em`                    |

---

## Spacing & Layout

- **Section gap (`--gap`):** `clamp(2.8rem, 5vw, 5rem)` — calm, unhurried rhythm
- **Main padding:** `clamp(2.8rem, 5.5vw, 5.5rem)` top / `clamp(1.4rem, 4vw, 6rem)` sides
- **Column measure:** prose max `65ch`; pull-quote max `54ch`; lede max `60ch`
- **Rail:** sticky `12rem` wide (scales with root font-size), border-right, collapses at 720px
- **Elnath block:** `--bg-alt` fill + `1.5px` accent top border only — no radius, no shadow
- **Radius: 0 everywhere.** Focus ring gets `border-radius: 1px` as sole exception.
- **No shadows. No gradients** except the single radial warm vignette on `body`.

---

## Responsive — Fluid Scaling

This build uses the same fluid system as `fluid-mid` and `fluid/index.html`:

### Root font-size

```css
html {
  font-size: clamp(15px, calc(0.45vw + 13px), 22px);
}
```

~15px at 360px viewport → ~22px at ~1700px. Every `rem`/`em` value on the page scales with it automatically — type, spacing, the rail width, all of it.

### Fluid shell

```css
.shell {
  width: min(94vw, 88rem);
  margin-inline: auto;
}
```

Uses wide screens fully (no dead side margins). At 360px: 94vw ≈ 338px. At large viewports: capped proportionally so it never feels like an infinite column.

### Fluid type

Hero H1 uses `clamp(2.8rem, 6.2vw, 7.5rem)` — the vw component ties the headline size to viewport width so the bold moment scales fluidly. Body text is capped to `65ch` for readability (same physical measure, larger text on wide screens).

### Fluid spacing

Side padding and section gaps use `clamp()` so breathing room grows proportionally at large viewports rather than staying fixed.

### Collapse breakpoint

At `max-width: 720px` the sticky rail collapses into a horizontal top bar. This is the only layout breakpoint — everything else is continuous fluid scaling.

---

## 4 Do

1. Let the hero breathe. The `opsz 144` Fraunces H1 at weight 700 is the one loud move — give it vertical room before the lede.
2. Use oxblood like a wax seal: one or two places per screen section, never repeated in a row.
3. Keep Newsreader body at `1rem` / lh `1.78` — the warmth lives in the leading, not the size.
4. Honor the `65ch` measure. At wide viewports, add whitespace to the right, never wider text.

## 4 Don't

1. Don't raise the hero weight above 700 or add a second opsz-144 element — the boldness is effective only because it's singular.
2. Don't use accent as a background or fill — oxblood is a stroke, border, and text color only.
3. Don't add shadows, heavy gradients, border-radius cards, or glowing elements.
4. Don't replace Newsreader body with Fraunces — the contrast between display and body is the whole flavor.

---

## Iteration Guide

To push warmer: shift `--bg` toward `#f2ead8` and `--accent` toward `#8c4030`. To pull back the bold-move: reduce hero weight to 500 and cap clamp at `5rem` — you get a more purely-F result. To add a second textural layer: try Fraunces smallcaps (`font-variant-caps: small-caps`) on the pull-quote attribution only.

To adjust fluid behavior: change the `0.45vw` coefficient in the root `clamp()` to scale faster (larger coefficient) or slower (smaller). The `88rem` shell cap controls how wide the layout grows before whitespace takes over.

---

## Known Gaps

- **Dark-mode vignette:** the `body` `background-image` radial gradient is light-mode tuned; in dark mode it may be too subtle — consider increasing opacity to `0.065` for dark.
- **Korean toggle** links to `href="#"` (placeholder); implement as `/ko/` when translation exists.
- **Fraunces opsz 144 download weight:** the variable font range 9–144 is a large file; add `font-display: swap` via a `@font-face` override if FOUT is observed on slow connections.
