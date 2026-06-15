# Fluid-Bold — Design Spec

## Signature

**Blend-Bold's look, Fluid's responsive system.** Identical aesthetic to blend-bold — Fraunces at `opsz 144 / weight 900` for the hero, warm paper palette (`#f6f1e8`), Newsreader body, oxblood accent family, sticky rail layout, IBM Plex Mono uppercase labels — but the entire page scales fluidly with viewport width via a `clamp()`-based root font-size and a `min(94vw, 88rem)` fluid shell. No dead side margins, no abrupt breakpoint jumps. The bold hero fills the content column proportionally at every width.

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

**Accent family is F's** (`#7c3a2c`/`#b85c47`). One accent; used only on: sphere mark, hero period, pull-quote 3px top-rule, Elnath card left+top border, em highlights, footer dot.

---

## Type Tokens

| Role             | Family          | Weight / Style        | opsz  | Size (fluid)                   | Tracking     |
|------------------|-----------------|-----------------------|-------|--------------------------------|--------------|
| Hero display     | Fraunces        | 900                   | 144   | `clamp(3rem, 7vw, 8rem)`       | `−0.03em`    |
| Section display  | Fraunces        | 700                   | 72    | `clamp(1.4rem, 2.8vw, 2.5rem)` | `−0.02em`    |
| Pull quote       | Fraunces italic | 300i                  | 72    | `clamp(1.2rem, 2.4vw, 1.75rem)` | default     |
| Section label    | IBM Plex Mono   | 500                   | —     | `0.72rem` (scales w/ root)     | `+0.18em`, UPPERCASE |
| Eyebrow          | IBM Plex Mono   | 500                   | —     | `0.72rem` (scales w/ root)     | `+0.18em`, UPPERCASE |
| Lede             | Newsreader      | 400                   | —     | `clamp(1rem, 1.8vw, 1.2rem)`   | default      |
| Body             | Newsreader      | 400                   | —     | `1rem`, lh `1.78`              | default      |
| Rail nav         | Fraunces italic | 300i                  | —     | `0.9rem` (scales w/ root)      | default      |
| Meta / sig       | IBM Plex Mono   | 400–500               | —     | `0.6–0.72rem`                  | `+0.08–0.12em`, UPPERCASE |

All `rem`/`em` values scale automatically with the fluid root font-size.

---

## Spacing & Radius

- `--rail-w`: `12rem` — scales with root font-size; wider on large screens
- `--pad-side`: `clamp(1.4rem, 4vw, 6rem)` — fluid side padding, fills wide screens
- `--pad-top`: `clamp(2.8rem, 5.5vw, 5.5rem)` — vertical breathing room
- `--gap`: `clamp(3rem, 7vw, 5.5rem)` — between major sections
- Body measure: `62ch` max; pull-quote `54ch`; lede `58ch`
- **Radius: 0 everywhere.** No softening on cards or any element.
- **No shadows.** Depth via border color + `--bg-alt` fill only.

---

## 4 Do

1. **Hero at opsz 144, weight 900.** The extreme thick/thin contrast is the defining move — do not reduce weight or opsz.
2. **All section eyebrows as IBM Plex Mono uppercase.** `letter-spacing: 0.18em` — the shared DNA of E and F.
3. **One accent, rationed to ~6 structural moments.** Mark, period, pull-quote top-rule, card border, em text, footer dot. Every new use dilutes it.
4. **Newsreader for all prose.** The shift from display Fraunces to humanist Newsreader body creates reading comfort despite the bold display — don't mix them up.

## 4 Don't

1. **No border-radius anywhere.** Squared corners are load-bearing to the research-house gravity.
2. **No shadows, gradients, or glows.** The single-direction border and bg-alt surface is the entire depth system.
3. **No accent on nav links or body text.** Reserve it for structural moments; hover states use `--ink-mid`.
4. **No AI visual clichés.** No purple/cyan, no node art, no glowing orbs — the sphere mark is enough.

---

## Responsive — Fluid Scaling

This build copies the fluid-mid responsive system exactly. No breakpoint jumps — everything scales continuously with viewport width.

### Root font-size

```css
html {
  font-size: clamp(15px, calc(0.45vw + 13px), 22px);
}
```

~15px at 360px viewport → ~22px at 1700px. All `rem`/`em` values throughout the page scale with this, so the entire proportional system grows together.

### Shell

```css
.shell {
  width: min(94vw, 88rem);
  margin-inline: auto;
}
```

At narrow widths: `94vw` keeps the page well-contained with slight edge margin. At wide widths: `88rem` × `22px` (max root size) caps at a proportional maximum — but the shell reaches this cap well before hitting it on most viewports, so the page always feels full, never column-in-the-middle.

### Fluid padding

```css
--pad-side: clamp(1.4rem, 4vw, 6rem);
--pad-top:  clamp(2.8rem, 5.5vw, 5.5rem);
--gap:      clamp(3rem, 7vw, 5.5rem);
```

All computed in `rem` (which themselves scale), so the proportional feel holds at every width without vw overrides.

### Fluid type

The hero uses `clamp(3rem, 7vw, 8rem)` — the vw component ensures the opsz-144 weight-900 Fraunces fills the content column proportionally at wide widths. Section displays and pull quotes use the same pattern.

### Narrow collapse (≤ 720px)

Rail collapses from sticky sidebar to horizontal top bar. Shell widens to `min(96vw, 88rem)`. Principles grid goes single-column. No horizontal scroll at any width.

---

## Known Gaps

- **No manual dark/light toggle** — relies on `prefers-color-scheme` only; add `data-theme` on `<html>` + one `<button>` to enable.
- **Korean translation** (`/ko/`) not implemented; lang toggle links to `href="#"`.
- **Fraunces `SOFT`/`WONK` axes** not set (optional); older WebKit falls back to Georgia cleanly.
- **Pull-quote on mobile (< 380px):** the 3px top border may feel disconnected at very narrow widths; consider adding a `padding-left: 0.75rem` and a left-border fallback.
