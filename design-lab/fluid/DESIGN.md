# Fluid — Viewport-Proportional Build of Blend-Mid

## North-Star Signature

Same as Blend-Mid: editorial research house at a confident, readable scale. Fraunces display + Newsreader body + IBM Plex Mono labels. Warm oxblood accent. The only change from Blend-Mid is the responsive/layout system — replaced with a fluid, viewport-proportional approach so the whole page scales smoothly as the window widens, with no abrupt breakpoint jumps and no empty side margins on wide screens.

---

## Color Tokens

| Token         | Light           | Dark            | Use                            |
|---------------|-----------------|-----------------|--------------------------------|
| `--bg`        | `#f6f1e8`       | `#181410`       | Page background                |
| `--bg-alt`    | `#efe9db`       | `#1f1b17`       | Elnath card fill               |
| `--surface`   | `#f9f5ef`       | `#231f1b`       | Reserved surface               |
| `--ink`       | `#2a241d`       | `#ede6da`       | Primary text                   |
| `--ink-mid`   | `#6b5f52`       | `#a49a8e`       | Body, secondary text           |
| `--ink-faint` | `#b0a598`       | `#4a4440`       | Labels, meta, stamps           |
| `--accent`    | `#7c3a2c`       | `#b85c47`       | Mark, period, borders, em      |
| `--rule`      | `#d9d0c3`       | `#302a24`       | Hairlines, card borders        |

**Accent family: warm oxblood `#7c3a2c` (light) / terracotta `#b85c47` (dark).** Used only on: sphere mark, hero period, pull-quote left border, Elnath card top border, emphasis text, footer dot.

---

## Type Tokens

| Role             | Font                   | Weight | opsz / variant | Size token                          | Tracking            |
|------------------|------------------------|--------|----------------|-------------------------------------|---------------------|
| Hero display     | Fraunces               | 700    | opsz 72        | `clamp(2.8rem, 6.2vw, 7.5rem)`     | `−0.025em`          |
| Pull quote       | Fraunces italic        | 300    | opsz 72        | `clamp(1.2rem, 2.2vw, 2rem)`       | default             |
| Section display  | Fraunces               | 600    | opsz 48        | `clamp(1.35rem, 2.6vw, 2.6rem)`    | `−0.018em`          |
| Section label    | IBM Plex Mono          | 500    | —              | `0.68rem`                           | `+0.16em`, UPPERCASE|
| Eyebrow          | IBM Plex Mono          | 400    | —              | `0.68rem`                           | `+0.14em`, UPPERCASE|
| Body             | Newsreader             | 400    | opsz auto      | `1rem`                              | default             |
| Lede             | Newsreader             | 400    | —              | `clamp(1rem, 1.7vw, 1.2rem)`       | default             |
| Rail nav         | Fraunces italic        | 300    | opsz 36        | `0.875rem`                          | default             |
| Meta / stamp     | IBM Plex Mono          | 400–500| —              | `0.6–0.68rem`                       | `+0.08–0.1em`       |

All sizes are in **rem/em** so they scale with the fluid root font-size automatically.

---

## Responsive — Fluid Scaling

This is the core difference from Blend-Mid. The system avoids hard breakpoints in favour of continuous scaling from ~360px to ~1700px+.

### 1. Fluid Root Font-Size

```css
html {
  font-size: clamp(15px, calc(0.45vw + 13px), 22px);
}
```

- At 360px viewport: `0.45 × 360 + 13 = 15.7px` → clamped to **15px**
- At 1024px: `0.45 × 1024 + 13 = 17.6px`
- At 1680px: `0.45 × 1680 + 13 = 20.6px`
- At 2000px+: clamped to **22px**

Because everything in the design is sized in `rem`/`em`, this single rule makes the entire page scale like a smooth zoom between those bounds. No individual property needs a media query for size changes.

### 2. Fluid Shell

```css
.shell {
  width: min(94vw, 88rem);
  margin-inline: auto;
}
```

- At 360px: `94vw = 338px` (keeps a small edge margin)
- At 1024px: `94vw = 963px` (fills the screen well)
- At 1680px: `94vw = 1579px` — the page uses 94% of the screen; no dead margins
- At very wide viewports: `88rem` kicks in (88 × 22px = 1936px max) so text never stretches uncomfortably

Side padding scales with a fluid `clamp(1.4rem, 4vw, 6rem)` so internal breathing room grows proportionally with the layout.

### 3. Rail Width in rem

```css
--rail-w: 12rem;
```

The sidebar rail is `12rem` (not `px`), so it grows with the root font-size: ~180px on mobile, ~247px at 1680px. It stays proportional to the text beside it.

### 4. Readability Guard

Paragraph text is capped at `65ch` (pull-quote at `54ch`). Because `ch` is relative to the element's font size, and the root font-size scales up on wide screens, the column renders **proportionally larger** while its line length in characters stays constant. This is the elegant property: measure is controlled by character count, physical size by the fluid root.

### 5. Single Structural Breakpoint

Only one real layout change: at `720px` the sticky side rail collapses into a horizontal top bar (same content, reordered as flexbox row). Below that the `shell` switches to a single-column grid. Everything else — spacing, type, padding — scales continuously via `clamp()`.

---

## Spacing & Rhythm

| Token        | Value                           | Use                              |
|--------------|---------------------------------|----------------------------------|
| `--pad-side` | `clamp(1.4rem, 4vw, 6rem)`     | Main horizontal padding          |
| `--pad-top`  | `clamp(2.8rem, 5.5vw, 5.5rem)` | Vertical section top padding     |
| `--gap`      | `clamp(2.8rem, 5vw, 5rem)`     | Between content sections         |
| `--prose-max`| `65ch`                          | Body text measure cap            |
| `--pull-max` | `54ch`                          | Pull-quote measure cap           |

- **Border radius: zero everywhere.** No pill shapes, no card softening.
- **No shadows, no gradients.** Depth via surface color and ruled borders only.

---

## 4 Do

1. **Keep everything in rem/em.** Any px value that should scale must be converted — otherwise it stays fixed and breaks the fluid proportioning.
2. **Test with browser zoom AND with viewport resize.** The clamp system handles viewport resize; browser zoom is handled by the fixed-px baseline + rem cascade.
3. **Let the prose-max ch-cap do its job.** Don't widen `--prose-max` beyond `68ch`; comfortable reading measure is the readability guard's point.
4. **Keep the single breakpoint at `720px`.** The rail collapse is the only structural rupture; all other adaptation is continuous.

## 4 Don't

1. **Don't add pixel-based widths or paddings.** They will stay fixed while the rest scales, breaking proportion.
2. **Don't add more breakpoints for font sizes.** The root clamp handles type scaling continuously — extra breakpoints fight it.
3. **Don't widen the shell beyond `88rem` max.** At that width with a 22px root, lines become too wide even with the ch-cap on prose.
4. **Don't remove the `min(94vw, …)`.** The vw part is what makes the page fill wide screens; without it the layout collapses to a narrow strip.

---

## Iteration Guide

- To make the page feel larger earlier (e.g. at 1200px): increase the `0.45vw` slope, e.g. `0.55vw + 12px`.
- To keep it tighter longer: decrease slope to `0.35vw + 14px`.
- To widen or narrow the shell: adjust the `88rem` max or the `94vw` fraction.
- To tilt type toward Blend-Mid's more restrained scale: reduce hero clamp max from `7.5rem` to `5rem`.

---

## Known Gaps (inherited from Blend-Mid)

- No manual light/dark toggle — relies on `prefers-color-scheme` only.
- Korean (`/ko/`) toggle links to `href="#"` (placeholder).
- Principles rendered as a ruled single-column list; a fluid two-column grid at wide widths is a future option.
- `font-display: swap` not set on Google Fonts URL; add `&display=swap` if FOUT is a problem (URL already includes it via the `display=swap` param in the `<link>` tag).
