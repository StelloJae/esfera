---
version: "1.0"
name: "Esfera Research Design System"
description: >
  Canonical design-system spec for Esfera Research — a warm scholarly editorial
  base (Fraunces + Newsreader + IBM Plex Mono) plus a bold Archivo Black poster
  hero. One warm accent, rationed. Fluid viewport-proportional scaling.
  Light/dark auto with manual override. Zero horizontal scroll, zero shadows.

colors:
  light:
    bg:        { value: "#f6f1e8", role: "Page background — warm cream paper" }
    bg-alt:    { value: "#efe9db", role: "Alternate surface — slightly cooler parchment; used for Elnath card" }
    surface:   { value: "#f9f5ef", role: "Elevated surface — lightest warm white; reserved for future modals/tooltips" }
    ink:       { value: "#2a241d", role: "Primary text — near-black warm brown" }
    ink-mid:   { value: "#5a4e43", role: "Secondary text — body prose, rail links" }
    ink-faint: { value: "#9a8e82", role: "Tertiary text — labels, metadata, dividers text" }
    accent:    { value: "#d5560a", role: "Aldebaran amber — the one warm accent; links, fills, marks, rules" }
    rule:      { value: "#ccc4b7", role: "Hairline dividers — warm gray-beige" }
  dark:
    bg:        { value: "#181410", role: "Page background — deep warm charcoal" }
    bg-alt:    { value: "#1f1b17", role: "Alternate surface — slightly lighter charcoal" }
    surface:   { value: "#231f1b", role: "Elevated surface — lightest dark warm tone" }
    ink:       { value: "#ede6da", role: "Primary text — warm off-white" }
    ink-mid:   { value: "#a49a8e", role: "Secondary text — muted warm tan" }
    ink-faint: { value: "#4a4440", role: "Tertiary text — very muted warm gray" }
    accent:    { value: "#f58a26", role: "Aldebaran amber dark-mode — brighter orange for contrast on dark" }
    rule:      { value: "#302a24", role: "Hairline dividers — near-invisible warm dark" }

typography:
  poster:
    fontFamily: '"Archivo Black", "Arial Black", sans-serif'
    fontSize: "clamp(2.2rem, 5.8vw, 9rem)"
    fontWeight: 400
    lineHeight: 0.93
    letterSpacing: "-0.025em"
    textTransform: uppercase
    role: "Poster hero headline only — never used elsewhere"
  display:
    fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
    fontSize: "clamp(1.35rem, 2.6vw, 2.6rem)"
    fontWeight: 600
    fontVariationSettings: '"opsz" 48'
    letterSpacing: "-0.018em"
    lineHeight: 1.2
    role: "Section display headings (h2.display)"
  post-title:
    fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
    fontSize: "clamp(2rem, 4.5vw, 4rem)"
    fontWeight: 600
    fontVariationSettings: '"opsz" 72'
    letterSpacing: "-0.025em"
    lineHeight: 1.1
    role: "Article/post page title (h1)"
  pull-quote:
    fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
    fontSize: "clamp(1.2rem, 2.2vw, 2rem)"
    fontWeight: 300
    fontStyle: italic
    fontVariationSettings: '"opsz" 72'
    lineHeight: 1.5
    role: "Pull question / large editorial aside"
  body:
    fontFamily: '"Newsreader", Georgia, "Times New Roman", serif'
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.78
    role: "All body prose — inherits fluid root font-size"
  post-h2:
    fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
    fontSize: "clamp(1.05rem, 1.8vw, 1.3rem)"
    fontWeight: 600
    fontVariationSettings: '"opsz" 48'
    letterSpacing: "-0.01em"
    role: "Article section subheadings"
  blockquote:
    fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
    fontSize: "clamp(1.05rem, 1.8vw, 1.35rem)"
    fontWeight: 300
    fontStyle: italic
    fontVariationSettings: '"opsz" 72'
    lineHeight: 1.55
    role: "Blockquote / inline pull-quote in article body"
  label:
    fontFamily: '"IBM Plex Mono", "Courier New", monospace'
    fontSize: "0.68rem"
    fontWeight: 500
    letterSpacing: "0.16em"
    textTransform: uppercase
    role: "Section eyebrow labels (h2.label)"
  meta:
    fontFamily: '"IBM Plex Mono", "Courier New", monospace'
    fontSize: "0.62rem"
    fontWeight: 400
    letterSpacing: "0.1em"
    textTransform: uppercase
    role: "Post-meta line, rail stamp, footer sig"
  brand-name:
    fontFamily: '"IBM Plex Mono", "Courier New", monospace'
    fontSize: "0.62rem"
    fontWeight: 500
    letterSpacing: "0.09em"
    textTransform: uppercase
    lineHeight: 1.35
    role: "Rail brand logotype text"
  rail-nav:
    fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
    fontSize: "0.875rem"
    fontWeight: 300
    fontStyle: italic
    fontVariationSettings: '"opsz" 36'
    lineHeight: 1.5
    role: "Rail navigation links"
  hero-eyebrow:
    fontFamily: '"IBM Plex Mono", "Courier New", monospace'
    fontSize: "0.68rem"
    letterSpacing: "0.18em"
    textTransform: uppercase
    color: "{colors.accent}"
    role: "Small uppercase label above poster headline"

spacing:
  root-font-size: "clamp(15px, calc(0.45vw + 13px), 22px)"
  shell-width: "min(94vw, 88rem)"
  shell-width-mobile: "min(96vw, 88rem)"
  rail-width: "12rem"
  pad-side: "clamp(1.4rem, 4vw, 6rem)"
  pad-top: "clamp(2.8rem, 5.5vw, 5.5rem)"
  gap: "clamp(2.8rem, 5vw, 5rem)"
  prose-max-landing: "none"
  prose-max-article: "66ch"
  pull-max: "54ch"

rounded:
  default: "0"
  note: "No border-radius anywhere. Depth is expressed through hairlines and color, never softened corners."

components:
  shell:
    description: "CSS Grid container, 2-column (rail + main), fluid width"
    columns: "var(--rail-w) 1fr"
    width: "{spacing.shell-width}"
    breakpoint-collapse: "720px — collapses to single column, rail becomes top bar"
  rail:
    description: "Sticky sidebar nav, 12rem wide, accent-stroked sphere mark + brand + lang toggle + theme toggle + nav links"
    position: "sticky, top: 0, height: 100vh"
    background: "{colors.bg}"
    borderRight: "1px solid {colors.rule}"
    padding: "{spacing.pad-top} 1.5rem {spacing.pad-top} 0"
    mark:
      size: "1.55rem × 1.55rem"
      stroke: "{colors.accent}"
      fill: none
      opacity: 0.88
      shape: "SVG engraved globe — outer circle r=12.5, meridian ellipse rx=5.2 ry=12.5, equatorial ellipse rx=12.5 ry=4.6; all stroke, no fill"
    brand-name: "{typography.brand-name}"
    lang-toggle:
      font: "{typography.meta}"
      active-color: "{colors.accent}"
      inactive-color: "{colors.ink-faint}"
    theme-toggle:
      font: "{typography.meta}"
      color: "{colors.ink-faint}"
      hover-color: "{colors.accent}"
      label-light: "☾ dark"
      label-dark: "☀ light"
    nav-links: "{typography.rail-nav}"
    hover-color: "{colors.accent}"
    separator:
      width: "1.5rem"
      height: "1px"
      background: "{colors.rule}"
      margin: "1.75rem 0"
    stamp:
      font: "{typography.meta}"
      color: "{colors.ink-faint}"
      content: "Est. 2026"
    mobile:
      layout: "flex-direction: row, flex-wrap: wrap"
      border: "border-bottom: 1px solid {colors.rule}"
      padding: "1.1rem 0"
      hidden-at-mobile: "rail-sep, rail-push, rail-stamp"
      railnav-mobile: "flex-direction: row, gap: 0 1.1rem, border-top: 1px solid {colors.rule}"
  poster-hero:
    description: >
      Full-width opening section of the landing page. Theme-aware background
      (var(--bg) — warm cream in light, warm charcoal in dark — never a forced dark band).
      Archivo Black uppercase headline broken into exactly three lines. Two lines
      use solid accent fill with knockout text. Faint decorative sphere behind type.
    element: "section.hero-band"
    background: "{colors.bg} via var(--hero-bg)"
    padding: "clamp(3rem, 7vw, 6.5rem) {spacing.pad-side} clamp(2.5rem, 5vw, 5rem)"
    overflow: hidden
    eyebrow:
      font: "{typography.hero-eyebrow}"
      marginBottom: "clamp(1.25rem, 2.5vw, 2rem)"
    headline:
      font: "{typography.poster}"
      color: "{colors.ink} via var(--hero-ink)"
      hyphens: none
      overflow-wrap: normal
      word-break: normal
      max-width: "100%"
      structure:
        line1: 'span.hl — "A LAB WITH" — plain ink, white-space: nowrap'
        line2: 'span.hl > span.hero-accent-fill — "NO" — KNOCKOUT: accent fill + color: var(--bg)'
        line3: 'span.hl > span.hero-accent-fill — "RESEARCHERS." — KNOCKOUT: accent fill + color: var(--bg)'
      knockout-rule: >
        hero-accent-fill uses background: var(--accent) and color: var(--bg).
        The text color equals the page surface color so letters appear as negative
        space cut through the orange fill. This is NEVER black — it must equal var(--bg).
        padding: 0.02em 0.1em 0.04em; box-decoration-break: clone.
      korean-variant:
        line1: '"연구원이 없는" — plain ink'
        line2: '"연구소." — accent fill knockout; word-break: keep-all'
    sphere-watermark:
      position: "absolute, right: -6%, top: 50%, translateY(-50%)"
      opacity: 0.06
      color: "{colors.accent} via currentColor"
      size: "640×640px (SVG viewBox 700×700)"
      overflow: hidden (contained within hero-band)
      z-index: 0
      pointer-events: none
      shape: "5-stroke engraved globe (outer circle + 4 ellipses at varying opacities)"
    lede:
      structure: "div.hero-lede-wrap with border-top: 1px solid var(--rule), marginTop: clamp(1.75rem, 3.5vw, 3rem)"
      font: "{typography.body}"
      fontSize: "clamp(0.92rem, 1.5vw, 1.1rem)"
      color: "{colors.ink-mid}"
      fontStyle: italic
      maxWidth: "58ch"
      em: "font-style: normal, color: {colors.ink}"
    accent-bar:
      description: "3px accent-colored horizontal rule separating hero from editorial body"
      height: "3px"
      background: "{colors.accent}"
      width: "100%"
  pull-quote:
    description: "Large italic serif question with accent left rule; used as central editorial anchor"
    element: "section.pull-block > p.pull-q"
    borderLeft: "2.5px solid {colors.accent}"
    paddingLeft: "1.5rem"
    maxWidth: "{spacing.pull-max}"
    font: "{typography.pull-quote}"
    color: "{colors.ink}"
    em: "font-style: normal, font-weight: 600, color: {colors.accent}"
  elnath-card:
    description: "Flagship callout card; bg-alt fill, accent top border, hairline other sides"
    element: "div.elnath-card"
    background: "{colors.bg-alt}"
    borderTop: "2px solid {colors.accent}"
    borderLeft: "1px solid {colors.rule}"
    borderRight: "1px solid {colors.rule}"
    borderBottom: "1px solid {colors.rule}"
    padding: "clamp(1.5rem, 2.8vw, 2.4rem)"
    title:
      font: "{typography.display}"
      fontSize: "clamp(1.25rem, 2vw, 2rem)"
    body:
      font: "{typography.body}"
      color: "{colors.ink-mid}"
      lineHeight: 1.76
    em: "font-style: italic, color: {colors.accent}"
  section-label:
    description: "Mono eyebrow label above sections (h2.label)"
    font: "{typography.label}"
    color: "{colors.ink-faint}"
    marginBottom: "1.25rem"
  display-heading:
    description: "Large serif section heading (h2.display)"
    font: "{typography.display}"
    color: "{colors.ink}"
  principles-list:
    description: "Ruled list of principles; hairline rules between items"
    borderBetween: "1px solid {colors.rule}"
    borderFirst: "border-top: 1px solid {colors.rule}"
    padding: "0.85rem 0"
    strong: "font-family: {typography.body.fontFamily}, font-weight: 600, color: {colors.ink}"
  studying-list:
    description: "Em-dash bullet list; accent em-dash, serif weight 300"
    gap: "0.9rem"
    bullet: 'content: "—", color: {colors.accent}, font-family: Fraunces, weight: 300'
    paddingLeft: "1.4rem"
    em: "font-style: italic, color: {colors.ink}"
  article-layout:
    description: "Reading layout for posts; prose capped at 66ch, large Fraunces title, accent title-rule"
    maxWidth: "{spacing.prose-max-article}"
    post-meta:
      font: "{typography.meta}"
      color: "{colors.ink-faint}"
      separator: "· colored {colors.rule}"
      marginBottom: "clamp(1rem, 2vw, 1.5rem)"
    title:
      font: "{typography.post-title}"
      color: "{colors.ink}"
    title-rule:
      borderTop: "2.5px solid {colors.accent}"
      width: "3.5rem"
      marginBottom: "clamp(1.5rem, 3vw, 2.5rem)"
    body-p:
      font: "{typography.body}"
      lineHeight: 1.82
      color: "{colors.ink-mid}"
      marginBottom: "1.15rem"
    h2:
      font: "{typography.post-h2}"
      color: "{colors.ink}"
      marginTop: "clamp(1.8rem, 3.5vw, 2.8rem)"
    blockquote:
      font: "{typography.blockquote}"
      borderLeft: "2.5px solid {colors.accent}"
      paddingLeft: "1.25rem"
      margin: "clamp(1.5rem, 3vw, 2.5rem) 0"
      em: "font-style: normal, font-weight: 600, color: {colors.accent}"
    ul-li:
      bullet: 'content: "—", color: {colors.accent}, font-family: Fraunces, weight: 300'
      paddingLeft: "1.4rem"
    links:
      color: "{colors.accent}"
      borderBottom: "1px solid color-mix(in srgb, var(--accent) 35%, transparent)"
      hover: "border-color: {colors.accent}"
    section-rule:
      borderTop: "1px solid {colors.rule}"
      margin: "clamp(1.8rem, 3.5vw, 3rem) 0"
    post-sig:
      font: "{typography.body}"
      fontStyle: italic
      color: "{colors.ink-faint}"
  footer:
    description: "Minimal hairline rule + mono stamp line with accent dot"
    rule:
      borderTop: "1px solid {colors.rule}"
      marginBottom: "1.375rem"
    sig:
      font: "{typography.meta}"
      letterSpacing: "0.08em"
      color: "{colors.ink-faint}"
    sig-dot:
      size: "0.32rem × 0.32rem"
      borderRadius: "50%"
      background: "{colors.accent}"
  theme-system:
    auto: "prefers-color-scheme: dark media query — :root:not([data-theme='light'])"
    manual: "data-theme attribute on <html> — 'light' or 'dark'"
    storage: "localStorage key: 'esfera-theme'"
    no-fouc: >
      Inline script in <head> before any CSS: reads localStorage and sets
      data-theme on documentElement before first paint. Required on every page.
    toggle-logic: "Reads current state from data-theme or matchMedia fallback; writes opposite; persists to localStorage"
---

# Esfera Research Design System

## Overview

Esfera Research is a warm scholarly editorial brand with a bold poster-hero
opening. The brand operates in two registers that share one palette:

1. **Scholarly editorial register** — Fraunces display headings, Newsreader
   body text, IBM Plex Mono for labels and metadata. Used on every page except
   the hero opening.
2. **Poster hero register** — Archivo Black, huge, uppercase, two words on solid
   accent fill with knockout type. Used exclusively in the landing page opening
   band.

Both registers share one warm accent: **Aldebaran amber**. The name is earned —
Aldebaran is the warm orange giant of Taurus, the same constellation as Elnath
(the star the flagship project is named after; Esfera means "celestial sphere").
The accent appears as `#d5560a` in light mode and `#f58a26` in dark mode.

No second accent exists. No shadows exist. No gradients exist. Decoration is
essentially zero. Depth is communicated through hairline rules, solid fills
(accent or bg-alt), and the knockout technique.

The entire system scales fluidly with the viewport. The root `font-size` is
`clamp(15px, calc(0.45vw + 13px), 22px)`, every measurement is in `rem`, and
the page shell is `min(94vw, 88rem)`. The page is physically proportional to the
viewport at every width, with no horizontal scroll possible.

---

## Colors

### Light Mode (default)

| Token        | Value      | Role                                                          |
|-------------|-----------|---------------------------------------------------------------|
| `--bg`      | `#f6f1e8` | Page background — warm cream paper                            |
| `--bg-alt`  | `#efe9db` | Alternate surface — slightly cooler parchment; Elnath card    |
| `--surface` | `#f9f5ef` | Elevated surface — lightest warm white; reserved              |
| `--ink`     | `#2a241d` | Primary text — near-black warm brown                          |
| `--ink-mid` | `#5a4e43` | Secondary text — body prose, nav links                        |
| `--ink-faint`| `#9a8e82` | Tertiary — labels, metadata, decorative text                  |
| `--accent`  | `#d5560a` | Aldebaran amber — the one warm accent                         |
| `--rule`    | `#ccc4b7` | Hairline dividers — warm gray-beige                           |

### Dark Mode

| Token        | Value      | Role                                                          |
|-------------|-----------|---------------------------------------------------------------|
| `--bg`      | `#181410` | Page background — deep warm charcoal                          |
| `--bg-alt`  | `#1f1b17` | Alternate surface — slightly lighter charcoal                 |
| `--surface` | `#231f1b` | Elevated surface — lightest dark warm tone                    |
| `--ink`     | `#ede6da` | Primary text — warm off-white                                 |
| `--ink-mid` | `#a49a8e` | Secondary text — muted warm tan                               |
| `--ink-faint`| `#4a4440` | Tertiary — very muted warm gray                               |
| `--accent`  | `#f58a26` | Aldebaran amber dark-mode — brighter orange for contrast      |
| `--rule`    | `#302a24` | Hairline dividers — near-invisible warm dark                  |

### The Accent Story

Aldebaran amber is the one accent this system will ever have. It names the brand
indirectly: Elnath is the beta star of Taurus; Aldebaran is Taurus's alpha —
the warm orange giant that fills your sky when you look at Elnath's constellation.
The color shifts between modes to maintain perceived warmth against different
backgrounds; it is the same color, not two different accents.

### Theme Switching

Theme switches automatically via `prefers-color-scheme: dark`. A manual toggle
overrides this by setting `data-theme="light"` or `data-theme="dark"` on
`<html>` and persisting to `localStorage` under the key `esfera-theme`. A
no-FOUC inline script must appear in `<head>` before any CSS on every page:

```html
<script>(function(){var t=localStorage.getItem('esfera-theme');if(t)document.documentElement.setAttribute('data-theme',t);})();</script>
```

The hero band uses `--hero-bg: var(--bg)` — it inherits the theme surface, not
a forced dark override. Both modes render correctly without any hero-specific
color tokens.

---

## Typography

### Font Stack

Four typefaces. One each for four distinct jobs. No substitution.

| Family | Variable | Use |
|--------|----------|-----|
| Archivo Black | `--f-poster` | Poster hero headline only |
| Fraunces | `--f-serif` | Display headings, pull quotes, rail nav, article titles |
| Newsreader | `--f-body` | All body prose |
| IBM Plex Mono | `--f-mono` | Labels, metadata, brand name, eyebrows, toggles |

Google Fonts load string (all four, with axes):
```
Archivo+Black&family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,300;1,9..144,400&family=Newsreader:ital,opsz,wght@0,6..72,400;0,6..72,500;1,6..72,400&family=IBM+Plex+Mono:wght@400;500
```

### Type Scale

| Token | Value | Use |
|-------|-------|-----|
| `--hero-poster` | `clamp(2.2rem, 5.8vw, 9rem)` | Poster hero — Archivo Black |
| `--hero` | `clamp(2.8rem, 6.2vw, 7.5rem)` | (reserved large display) |
| `--h2-disp` | `clamp(1.35rem, 2.6vw, 2.6rem)` | Display section headings |
| `--pull-q` | `clamp(1.2rem, 2.2vw, 2rem)` | Pull question |
| `--body` | `1rem` | Body prose (inherits fluid root) |
| `--small` | `0.68rem` | Labels, eyebrows, meta |
| post-title | `clamp(2rem, 4.5vw, 4rem)` | Article h1 |
| blockquote | `clamp(1.05rem, 1.8vw, 1.35rem)` | In-article blockquote |

The clamp floor on `--hero-poster` (2.2rem) is calibrated so "RESEARCHERS."
(the longest word) fits the available column width at a 390px viewport without
horizontal overflow.

### Optical Sizing

Fraunces uses `opsz` axis. Vary by size:
- `"opsz" 72` — post title, pull quote
- `"opsz" 48` — display headings, article h2
- `"opsz" 36` — rail nav links

### Root Font Size

```css
html { font-size: clamp(15px, calc(0.45vw + 13px), 22px); }
```

Everything else uses `rem`. This one declaration makes the entire page scale
proportionally. Do not override `font-size` on `html` for any reason.

---

## Layout

### Shell

```css
.shell {
  display: grid;
  grid-template-columns: var(--rail-w) 1fr; /* 12rem rail + fluid main */
  width: min(94vw, 88rem);
  margin-inline: auto;
  min-height: 100vh;
}
```

### Rail

Fixed `12rem` wide. Sticky, occupies full viewport height. Contains: sphere
mark, brand name, lang toggle, theme toggle, separator, nav links, spacer, stamp.

### Main Column

No fixed width — it is the remaining grid fraction after the rail. The column
must include `min-width: 0` and `overflow-x: hidden` to prevent grid child
overflow. There is no cap on body prose width on the landing page
(`--prose-max: none`); article pages cap at `66ch`.

### Breakpoint

At `≤720px`: shell collapses to a single column (`grid-template-columns: 1fr`,
`width: min(96vw, 88rem)`). The rail becomes a horizontal top bar
(`flex-direction: row`, `border-bottom: 1px solid var(--rule)`). `rail-sep`,
`rail-push`, and `rail-stamp` are hidden. Nav links go horizontal.

### Spacing Tokens

| Token | Value | Role |
|-------|-------|------|
| `--rail-w` | `12rem` | Rail width |
| `--pad-side` | `clamp(1.4rem, 4vw, 6rem)` | Horizontal padding inside main sections |
| `--pad-top` | `clamp(2.8rem, 5.5vw, 5.5rem)` | Vertical section top padding |
| `--gap` | `clamp(2.8rem, 5vw, 5rem)` | Vertical gap between major sections |

---

## Elevation & Depth

This system has no shadows and no gradients. Depth is communicated by:

1. **Hairlines** — `1px solid var(--rule)` for horizontal rules, rail border,
   card borders, section separators.
2. **Accent rules** — `2px–2.5px solid var(--accent)` for pull-quote left rule,
   Elnath card top border, title-rule, hero accent bar.
3. **Fill contrast** — `--bg-alt` on Elnath card creates depth without shadow.
4. **Knockout type** — the deepest "elevation" effect in the system is the
   poster hero: solid accent fill with text cut through it in the page surface
   color. No shadow makes it possible.

Border-radius is `0` everywhere. Do not introduce radius.

---

## Shapes

### Sphere Mark (brand logomark)

SVG, `1.55rem × 1.55rem`, `stroke: var(--accent)`, `fill: none`,
`stroke-width: 1.15`, `opacity: 0.88`. Three paths:

```html
<circle cx="16" cy="16" r="12.5"/>
<ellipse cx="16" cy="16" rx="5.2" ry="12.5"/>   <!-- meridian -->
<ellipse cx="16" cy="16" rx="12.5" ry="4.6"/>   <!-- equatorial -->
```

### Sphere Watermark (hero background)

SVG, `640×640` rendered, `viewBox="0 0 700 700"`. Five strokes, two with
`opacity="0.55"`. Color via `currentColor` set to `var(--accent)`. Global
`opacity: 0.06` on the element. Positioned absolute inside the hero band
(`right: -6%, top: 50%, translateY(-50%)`), clipped by `overflow: hidden` on
the band.

```html
<circle cx="350" cy="350" r="338" stroke="currentColor" stroke-width="2"/>
<ellipse cx="350" cy="350" rx="128" ry="338" stroke="currentColor" stroke-width="2"/>
<ellipse cx="350" cy="350" rx="338" ry="118" stroke="currentColor" stroke-width="2"/>
<ellipse cx="350" cy="350" rx="255" ry="338" stroke="currentColor" stroke-width="1" opacity="0.55"/>
<ellipse cx="350" cy="350" rx="338" ry="236" stroke="currentColor" stroke-width="1" opacity="0.55"/>
```

### Sig Dot

`0.32rem × 0.32rem`, `border-radius: 50%`, `background: var(--accent)`.
The only non-zero radius in the system, and it is decorative only.

---

## Components

### Rail Nav

Sticky left sidebar. Structure from top to bottom:

1. **Brand block** — sphere mark SVG + "Esfera / Research" in `--f-mono`.
2. **Lang + theme row** — "EN · 한국어 · ☾ dark" in `--f-mono` 0.6rem.
   Active lang in `var(--accent)`. Theme toggle: no border, no background;
   hover color is `var(--accent)`.
3. **Separator** — `1.5rem` wide, `1px` tall, `var(--rule)`.
4. **Nav links** — Fraunces italic weight-300 `opsz-36`, color `var(--ink-mid)`,
   hover `var(--accent)`.
5. **Spacer** — `flex: 1`.
6. **Stamp** — "Est. 2026" in `--f-mono` uppercase `var(--ink-faint)`.

### Poster Hero

Applied only to `index.html` (and its Korean equivalent). This component is the
sole use of Archivo Black.

The headline is always exactly three `span.hl` blocks (`display: block`,
`white-space: nowrap`):
- Line 1: `"A LAB WITH"` — plain `var(--ink)` text.
- Line 2: `"NO"` — wrapped in `span.hero-accent-fill`.
- Line 3: `"RESEARCHERS."` — wrapped in `span.hero-accent-fill`.

**Korean variant:**
- Line 1: `"연구원이 없는"` — plain ink (`word-break: keep-all`)
- Line 2: `"연구소."` — `span.hero-accent-fill`

**Knockout rule (non-negotiable):**
```css
.hero-accent-fill {
  background: var(--accent);
  color: var(--bg);   /* equals the page surface — never black */
  padding: 0.02em 0.1em 0.04em;
  -webkit-box-decoration-break: clone;
  box-decoration-break: clone;
}
```
The letters read as negative space cut through the amber fill because the text
color matches the page background. In light mode `var(--bg)` is `#f6f1e8`; in
dark mode it is `#181410`. The system handles both automatically.

The sphere watermark sits behind the headline at `z-index: 0`; all headline
elements are at `z-index: 1`.

Below the headline, `div.hero-lede-wrap` has `border-top: 1px solid var(--rule)`
and contains a single italic paragraph in Newsreader at
`clamp(0.92rem, 1.5vw, 1.1rem)`, color `var(--ink-mid)`, max-width `58ch`.

A 3px accent bar (`span.hero-accent-bar`, `background: var(--accent)`)
separates the hero from the editorial body.

### Pull Quote

Left rule, Fraunces italic light, max-width `54ch`. Emphasis within pull text
uses `font-style: normal; font-weight: 600; color: var(--accent)`.

### Elnath Card

`--bg-alt` fill. Border: `2px accent top`, `1px rule left/right/bottom`.
No radius. The "accent top border, neutral sides" pattern is reserved for the
flagship card — do not reuse for generic cards.

### Section Labels (Eyebrows)

IBM Plex Mono, `0.68rem`, `0.16em` letter-spacing, uppercase, `var(--ink-faint)`.
Used as `h2.label` above display headings. Never replace with a serif.

### Display Headings

Fraunces semi-bold, `clamp(1.35rem, 2.6vw, 2.6rem)`, `opsz 48`,
letter-spacing `-0.018em`, line-height `1.2`, `var(--ink)`.

### Principles List

Ruled list: each `<li>` has `padding: 0.85rem 0`, `border-bottom: 1px solid var(--rule)`. First item also has `border-top`. Bold terms inside use Fraunces
semi-bold weight-600, inline, `var(--ink)`.

### Studying / Bullet List

Em-dash bullets. The `::before` pseudo-element renders `"—"` in
`var(--accent)`, Fraunces weight-300. Content `padding-left: 1.4rem`.

### Article Layout

Distinct from the landing page. Rail identical. Main column:
`padding: var(--pad-top) var(--pad-side) calc(var(--pad-top) × 1.6)`.

Inside `article.post` (`max-width: 66ch`):
- **Post-meta line** — mono uppercase `0.62rem`, `var(--ink-faint)`, separator
  `·` colored `var(--rule)`.
- **h1.post-title** — Fraunces semi-bold `clamp(2rem, 4.5vw, 4rem)` `opsz 72`,
  letter-spacing `-0.025em`, line-height `1.1`.
- **hr.title-rule** — `2.5px solid var(--accent)`, width `3.5rem`.
- **Body paragraphs** — Newsreader `1rem`, line-height `1.82`, `var(--ink-mid)`,
  margin-bottom `1.15rem`.
- **h2 section headings** — Fraunces semi-bold `clamp(1.05rem, 1.8vw, 1.3rem)`
  `opsz 48`, letter-spacing `-0.01em`.
- **blockquote** — Fraunces light italic `clamp(1.05rem, 1.8vw, 1.35rem)`
  `opsz 72`, `border-left: 2.5px solid var(--accent)`, `padding-left: 1.25rem`.
  Emphasis within: `font-style: normal; font-weight: 600; color: var(--accent)`.
- **ul** — em-dash bullets, same as studying list.
- **Links** — `color: var(--accent)`,
  `border-bottom: 1px solid color-mix(in srgb, var(--accent) 35%, transparent)`,
  hover brings border to full accent.
- **hr.section-rule** — `1px solid var(--rule)`, margin `clamp(1.8rem, 3.5vw, 3rem) 0`.
- **Post signature** — Newsreader italic `var(--ink-faint)`.

### Footer

A horizontal hairline rule (`1px solid var(--rule)`) followed by a mono stamp
line. The stamp is `0.62rem` uppercase `0.08em` letter-spacing `var(--ink-faint)`,
preceded by a `0.32rem` accent dot.

---

## Do's and Don'ts

### Do's

- **Do use `var(--accent)` for every accent need** — the sphere mark stroke,
  the hero fill, left rules, title rules, bullet em-dashes, link colors,
  hover states, focus outlines. One color, many applications.
- **Do write every measurement in `rem`** — even `0.32rem` for the sig dot.
  Nothing in `px` after the root font-size declaration.
- **Do apply `min-width: 0` to all grid children** — this is what prevents
  grid items from overflowing their track.
- **Do include the no-FOUC script in `<head>` before any `<link rel="stylesheet">`
  or `<style>` on every page.**
- **Do set `hyphens: none; overflow-wrap: normal; word-break: normal` on the
  poster headline** — the clamp already prevents overflow; browser auto-hyphenation
  would break "RESEARCHERS." mid-word.
- **Do use `white-space: nowrap` on each `.hl` span** — the three headline lines
  are editorially fixed; they must never reflow.
- **Do use `overflow: hidden` on `.hero-band`** — the sphere watermark extends
  beyond the hero area and must be clipped.
- **Do apply `prefers-color-scheme` with the `:root:not([data-theme="light"])`
  guard** — this lets the manual toggle override OS preference without fighting
  the media query.
- **Do use `opsz` variation settings on Fraunces** — the font is a variable face;
  optical sizing at the rendered size is part of the type system.
- **Do keep all accent usage rationed** — accent communicates "this matters".
  If everything is accent-colored, nothing is.

### Don'ts

- **Don't put black (or `var(--ink)`) text on the accent fill** — the knockout
  text on `hero-accent-fill` must be `color: var(--bg)` (the page surface color).
  If it is black, the contrast with the amber fill is wrong and the "cut-out"
  reading is lost. This is the single most important rule in the system.
- **Don't introduce a second accent color** — not blue for links, not green for
  success states, not a second orange shade. One accent, always `var(--accent)`.
- **Don't let any element cause horizontal scroll** — enforce `overflow-x: hidden`
  on `html`, `body`, and `.main`; `min-width: 0` on `.main` and all grid
  children; `max-width: 100%` on the hero headline. Test at 320px.
- **Don't use Archivo Black anywhere except the poster hero** — it is a display
  face with one weight and no optical sizes. Fraunces handles all other display
  needs.
- **Don't force a dark hero band in light mode** — the hero uses `var(--bg)`,
  not a fixed dark background. In light mode the hero is cream. In dark mode it
  is dark charcoal. The same markup works for both.
- **Don't use `px` for layout measurements** — the fluid scaling system only
  works if spacing, type, and layout are in `rem` relative to the fluid root
  font-size.
- **Don't add `border-radius`** — except the `50%` sig dot, which is decorative
  and not a UI element. All interactive elements (buttons, cards, inputs) are
  sharp-cornered.
- **Don't add shadows** — not `box-shadow`, not `drop-shadow`, not `text-shadow`.
  Depth comes from hairlines and fill contrast.
- **Don't use gradients** — including subtle backgrounds. All fills are flat.
- **Don't hyphenate "RESEARCHERS."** — or any word in the poster headline. The
  `hyphens: none` rule is mandatory on `.hero-headline`. If the word causes
  overflow at a narrow viewport, lower the clamp floor of `--hero-poster` rather
  than allowing a hyphen.
- **Don't override `font-size` on `html`** — the single `clamp()` declaration
  governs the whole scale. A local override on `html` breaks the fluid system.
- **Don't add a second display font** — Fraunces is the display face for all
  non-hero headings. A second display font would fragment the editorial register.
- **Don't use `overflow: visible` on `hero-band`** — the sphere watermark will
  bleed into adjacent sections.
- **Don't use hardcoded light or dark hex values in component CSS** — always
  reference a token (`var(--bg)`, `var(--ink-mid)`, etc.) so theme switching
  works automatically.

---

## Responsive Behavior

### Breakpoints

| Breakpoint | Behavior |
|-----------|---------|
| `> 720px` | Two-column shell: `var(--rail-w) 1fr`. Rail is sticky sidebar. |
| `≤ 720px` | Single-column shell. Rail becomes horizontal top bar with `border-bottom`. Rail-sep, rail-push, and rail-stamp hidden. Nav links go horizontal. |

### Fluid Scaling

Everything scales proportionally between the `clamp()` floor and cap because the
root font-size is fluid and all other values are in `rem`. There are no discrete
breakpoints for type or spacing — the page is continuously responsive.

At `390px` (smallest iPhone viewport):
- Shell width: `min(94vw, 88rem)` → `~366px`
- Root font-size: `clamp(15px, calc(0.45vw + 13px), 22px)` → `~14.76px` → `15px` (floor)
- Hero poster: `clamp(2.2rem, 5.8vw, 9rem)` → `~2.2rem = 33px` at floor
- "RESEARCHERS." at `2.2rem` Archivo Black fits within `~337px` of usable column
  width without overflow.

### Testing Checklist

- No horizontal scrollbar at `320px`.
- Hero poster headline stays on three lines at all widths.
- "RESEARCHERS." never hyphenates.
- Theme toggle shows correct icon in both modes.
- No FOUC on page load.
- Rail collapses correctly at `720px`.
- Focus outlines visible (`2px solid var(--accent), offset 3px`) in both themes.

---

## Iteration Guide

Steps an AI design tool follows to generate a new Esfera page in this system:

1. **Copy the no-FOUC script** into `<head>` before any `<style>` or `<link>`.

2. **Load all four fonts** via the Google Fonts URL string specified in the
   Typography section.

3. **Paste the full token block** — both `:root` light tokens and the dark
   overrides for `@media (prefers-color-scheme: dark)` with the
   `:root:not([data-theme="light"])` guard, and `[data-theme="dark"]`.

4. **Set root font-size** on `html`:
   `font-size: clamp(15px, calc(0.45vw + 13px), 22px)`.

5. **Set overflow guards** on `html` (`overflow-x: hidden`), `body`
   (`overflow-x: hidden; max-width: 100%`), and `.main`
   (`min-width: 0; max-width: 100%; overflow-x: hidden`).

6. **Build the shell** as a 2-column CSS Grid with the rail at `var(--rail-w)`
   and the main column as `1fr`. Copy the `≤720px` breakpoint collapse.

7. **Build the rail** as a sticky sidebar with the sphere mark SVG, brand name,
   lang row, theme toggle, separator, nav links, spacer, and stamp. Copy the
   theme toggle script verbatim.

8. **Decide: does this page have a poster hero?** Only the landing page
   (`index.html`) and its Korean mirror do.
   - If yes: add `section.hero-band` with the sphere watermark SVG, eyebrow,
     three-line `h1.hero-headline` with `hero-accent-fill` spans on lines 2–3,
     lede-wrap paragraph, and the 3px `span.hero-accent-bar`.
   - If no: begin main content with padding `var(--pad-top) var(--pad-side)`.

9. **For article/post pages**: wrap content in `article.post` with
   `max-width: 66ch`. Include post-meta, `h1.post-title`, `hr.title-rule`
   (2.5px accent, 3.5rem wide), then body prose.

10. **Place the footer**: `hr.foot-rule` + `.sig` with accent dot and mono text.

11. **Check all colors reference tokens**, not hardcoded hex values.

12. **Verify the checklist** in the Responsive Behavior section before shipping.

---

## Known Gaps

The following content primitives exist in the research/product roadmap but are
not yet designed or specified in this system:

- **Paper cards** — How a published research paper appears in a listing: title,
  authors (AI agent names), date, abstract excerpt, PDF/link. No decision yet
  on whether these are card-shaped or row-shaped, how tags/categories display,
  or how the accent is used.

- **Citation rows** — Inline or footnote citations referencing prior work.
  Format, numbering style, and hover/expand behavior are undefined.

- **Failure log / graveyard timeline** — A chronological list of dead
  experiments. Design questions open: timeline spine treatment (vertical rule?
  accent dots?), how "dead" is communicated visually (faint ink? strikethrough?
  struck-accent?), whether entries have expandable detail or are permanently
  collapsed.

- **Dataset listings** — Cards or rows for public datasets released or used by
  the lab. License badges, size, format, and download link treatment are not
  yet designed.

- **Post index / archive** — The `/posts/` listing page. Number of items per
  page, sort order display, tag filtering UI, and pagination pattern are not
  yet specified.

- **Korean (ko/) pages** — The Korean register uses the same token system and
  layout, but the poster hero headline uses `word-break: keep-all` and the
  knockout fill is on `"연구소."` rather than a two-word split. Full Korean
  typography review (line-height, Fraunces in Hangul fallback) is pending.
