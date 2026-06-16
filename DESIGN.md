---
version: "2.0"
name: "Esfera Research Design System"
description: >
  Canonical design-system spec for Esfera Research — a cosmic scholarly editorial
  base (Fraunces + Newsreader + IBM Plex Mono) plus a bold Archivo Black knockout
  poster pattern. One main accent (starlight/periwinkle) plus three cosmic
  sub-accents (blue, violet, pink), rationed. Fluid viewport-proportional scaling.
  Light/dark auto with manual override. Zero horizontal scroll, zero shadows.

  This DESIGN.md is the reusable SYSTEM (the HOW). It is meant to be used WITH
  a per-page content brief that supplies copy and intent (the WHAT). For content
  pages (posts, lab notes), the markdown content itself serves as the page brief.
  No copy, file names, or page-specific decisions live in this document.

colors:
  light:
    bg:           { value: "#eef0f8", role: "Page background — pale cool dawn blue-lavender; NEVER warm cream" }
    bg-alt:       { value: "#e4e8f3", role: "Alternate surface — slightly deeper blue-lavender; callout cards" }
    surface:      { value: "#f7f8fc", role: "Elevated surface — lightest cool white; reserved for future modals/tooltips" }
    ink:          { value: "#181a2b", role: "Primary text — deep cosmic indigo, not pure black" }
    ink-mid:      { value: "#51566e", role: "Secondary text — body prose, rail links" }
    ink-faint:    { value: "#888ea6", role: "Tertiary text — labels, metadata, dividers text" }
    rule:         { value: "#d5d9e8", role: "Hairline dividers — cool blue-gray" }
    accent:       { value: "#4a57a6", role: "Main starlight/periwinkle accent — links, fills, marks, rules" }
    accent-blue:  { value: "#3a52d6", role: "Cosmic blue sub-accent — sphere meridian, eyebrow tints, small rules" }
    accent-violet:{ value: "#7a3fd0", role: "Cosmic violet sub-accent — pull-quote rule, knockout gradient midpoint" }
    accent-pink:  { value: "#cf3f86", role: "Cosmic pink sub-accent — sphere latitude, knockout gradient end, sig dot" }
  dark:
    bg:           { value: "#0a0b12", role: "Page background — deep void/night" }
    bg-alt:       { value: "#11131d", role: "Alternate surface — slightly lighter void" }
    surface:      { value: "#141622", role: "Elevated surface — lightest dark tone" }
    ink:          { value: "#eef1fa", role: "Primary text — starlight white" }
    ink-mid:      { value: "#8c92a8", role: "Secondary text — muted cosmic lavender" }
    ink-faint:    { value: "#4e5364", role: "Tertiary text — very muted space gray" }
    rule:         { value: "#20232f", role: "Hairline dividers — near-invisible dark" }
    accent:       { value: "#c4cdf0", role: "Main accent in dark — starlight/periwinkle, brighter for contrast on void" }
    accent-blue:  { value: "#5b7cff", role: "Cosmic blue sub-accent dark" }
    accent-violet:{ value: "#9d5cff", role: "Cosmic violet sub-accent dark" }
    accent-pink:  { value: "#ff5fa8", role: "Cosmic pink sub-accent dark" }

typography:
  poster:
    fontFamily: '"Archivo Black", "Arial Black", sans-serif'
    fontSize: "clamp(2.2rem, 5.8vw, 9rem)"
    fontWeight: 400
    lineHeight: 0.93
    letterSpacing: "-0.025em"
    textTransform: uppercase
    role: "Knockout poster headline only — never used elsewhere"
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
    description: "Sticky sidebar nav, 12rem wide, multi-stroke sphere mark + brand + lang toggle + theme toggle + nav links"
    position: "sticky, top: 0, height: 100vh"
    background: "{colors.bg}"
    borderRight: "1px solid {colors.rule}"
    padding: "{spacing.pad-top} 1.5rem {spacing.pad-top} 0"
    mark:
      size: "1.55rem × 1.55rem"
      stroke-outer: "{colors.accent}"
      stroke-meridian: "{colors.accent-blue}"
      stroke-equatorial: "{colors.accent-violet}"
      fill: none
      opacity: 0.9
      shape: "SVG wireframe globe — outer circle r=12.5 (accent), meridian ellipse rx=5.2 ry=12.5 (accent-blue), equatorial ellipse rx=12.5 ry=4.6 (accent-violet); all stroke, no fill"
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
  knockout-poster:
    description: >
      Full-width opening section used on pages that open with a bold brand
      statement (typically one such page per site). Theme-aware background
      (var(--bg) — pale dawn blue-lavender in light, deep void in dark — never
      a forced dark band). Archivo Black uppercase headline of 2–4 lines; 1–2
      lines MAY carry the knockout gradient fill. Headline copy and which lines
      receive fill are determined by the page brief, not this spec.
    element: "section.hero-band"
    background: "{colors.bg} via var(--bg)"
    padding: "clamp(3rem, 7vw, 6.5rem) {spacing.pad-side} clamp(2.5rem, 5vw, 5rem)"
    overflow: hidden
    eyebrow:
      font: "{typography.hero-eyebrow}"
      marginBottom: "clamp(1.25rem, 2.5vw, 2rem)"
    headline:
      font: "{typography.poster}"
      color: "{colors.ink} via var(--ink)"
      hyphens: none
      overflow-wrap: normal
      word-break: normal
      max-width: "100%"
      structure: >
        2–4 span.hl blocks (display: block; white-space: nowrap).
        Lines designated for knockout fill in the page brief are wrapped in
        span.hero-accent-fill. Plain lines remain bare span.hl in var(--ink).
        The count and fill assignment come from [page brief].
      knockout-rule: >
        hero-accent-fill uses a gradient background (blue→violet→pink) and
        color: var(--bg) — the text color equals the page surface so letters
        appear as negative space cut through the cosmic gradient fill.
        Dark: gradient #5b7cff→#9d5cff→#ff5fa8, text color #0a0b12 (void).
        Light: gradient #3a52d6→#7a3fd0→#cf3f86, text color #eef0f8 (dawn).
        This is NEVER black — it must equal var(--bg).
        padding: 0.02em 0.1em 0.04em; box-decoration-break: clone.
      knockout-css: >
        .hero-accent-fill {
          background: linear-gradient(100deg,
            var(--accent-blue) 0%,
            var(--accent-violet) 55%,
            var(--accent-pink) 100%);
          color: var(--bg);
          padding: 0.02em 0.1em 0.04em;
          -webkit-box-decoration-break: clone;
          box-decoration-break: clone;
        }
      line-count-examples:
        landing-style: "3 lines / 2 filled (bold multi-word assertion)"
        about-style: "2 lines / 1 filled (softer single emphasis)"
        error-style: "1 line / 1 filled (stark single statement)"
      clamp-calibration: >
        The clamp floor (2.2rem) must be verified against the page brief: the
        longest word in the poster headline must fit within the usable column at
        320–390px without horizontal overflow, and must never auto-hyphenate.
        Lower the floor if needed; do not relax hyphens: none.
    nebula-glow:
      description: "Radial gradient glow in blue/violet/pink hues. Occupies the hero-band via ::before pseudo-element."
      position: "absolute, inset: 0"
      z-index: 0
      pointer-events: none
      opacity: "var(--nebula-opacity) — 1 in dark (full atmosphere), 0.07 in light (subtle dawn wash)"
      gradients: >
        radial-gradient(ellipse 60% 55% at 76% 22%, rgba(91,124,255,0.15) 0%, rgba(157,92,255,0.11) 42%, rgba(255,95,168,0.05) 68%, transparent 88%)
        + two smaller supplementary radials in violet and pink at upper-right
    celestial-sphere:
      description: "Wireframe SVG globe, upper-right focal point of the hero. Multi-color strokes."
      element: "svg.hero-sphere-bg"
      position: "absolute, right: -4%, top: -2%"
      size: "clamp(360px, 56vw, 760px)"
      z-index: 0
      pointer-events: none
      strokes:
        outer-circle: "stroke: var(--accent), stroke-width: 1.8, opacity: 0.45"
        primary-meridian: "stroke: var(--accent-blue), stroke-width: 2.0, opacity: 0.55"
        equator: "stroke: var(--accent-violet), stroke-width: 2.0, opacity: 0.55"
        wide-meridian: "stroke: var(--accent), stroke-width: 1.2, opacity: 0.28"
        secondary-latitude: "stroke: var(--accent), stroke-width: 1.2, opacity: 0.28"
        pink-latitude: "stroke: var(--accent-pink), stroke-width: 1.4, opacity: 0.35"
        narrow-meridian: "stroke: var(--accent-blue), stroke-width: 1.0, opacity: 0.22"
        pole-dots: "fill: var(--accent), opacity: 0.40"
    starfield:
      description: >
        Fixed SVG behind all content. Multi-tint stars using CSS class fills
        (s-w white/ink, s-sl starlight, s-b blue, s-v violet, s-pk pink) so they
        respond to theme via CSS custom property fills. Overall opacity controlled
        by --starfield-opacity: 1 in dark (full void), 0.18 in light (dawn sky
        has few visible stars — fitting the '여명' look with deep-ink dots).
        Twinkle animation (twinkle-a/b/c keyframes) on select bright stars.
        Must respect prefers-reduced-motion.
      element: "svg#starfield"
      position: "fixed, inset: 0"
      z-index: 0
      pointer-events: none
      opacity: "var(--starfield-opacity)"
      animation: "twinkle-a (3.8s), twinkle-b (5.1s), twinkle-c (4.5s) — all suspended when prefers-reduced-motion: reduce"
    accent-bar:
      description: "1px gradient rule separating poster from editorial body; cosmic gradient across all sub-accents"
      height: "1px"
      background: "linear-gradient(90deg, var(--accent-blue) 0%, var(--accent) 40%, var(--accent-violet) 72%, var(--accent-pink) 100%)"
      opacity: 0.3
      width: "100%"
    lede:
      description: "Optional italic paragraph below headline. Copy from [page brief]."
      structure: "div.hero-lede-wrap with border-top: 1px solid var(--rule), marginTop: clamp(1.75rem, 3.5vw, 3rem)"
      font: "{typography.body}"
      fontSize: "clamp(0.92rem, 1.5vw, 1.1rem)"
      color: "{colors.ink-mid}"
      fontStyle: italic
      maxWidth: "58ch"
      em: "font-style: normal, color: {colors.ink}"
  pull-quote:
    description: "Large italic serif question with cosmic left rule; used as central editorial anchor"
    element: "section.pull-block > p.pull-q"
    borderLeft: "1px solid {colors.accent-violet}"
    paddingLeft: "1.5rem"
    maxWidth: "{spacing.pull-max}"
    font: "{typography.pull-quote}"
    color: "{colors.ink}"
    em: "font-style: normal, font-weight: 600, color: {colors.accent}"
  callout-card:
    description: >
      High-priority callout card. bg-alt fill, 1px accent-blue top border, 1px rule
      on left/right/bottom. No radius. Use for one high-priority callout per
      section. The landing page's flagship/Elnath block is the canonical example
      of this pattern.
    element: "div.callout-card"
    background: "{colors.bg-alt}"
    borderTop: "1px solid {colors.accent-blue}"
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
  post-index-row:
    description: >
      Archive list row for post/paper indexes. Minimal horizontal layout:
      mono date on the left, Fraunces title in the center, optional tag pills
      on the right. Separated from adjacent rows by a hairline rule.
    element: "li.post-index-row"
    borderBottom: "1px solid {colors.rule}"
    padding: "0.75rem 0"
    display: "grid, grid-template-columns: 7ch 1fr auto, align-items: baseline, gap: 0 1.25rem"
    date:
      font: "{typography.meta}"
      color: "{colors.ink-faint}"
      whiteSpace: nowrap
    title:
      fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
      fontSize: "clamp(0.95rem, 1.6vw, 1.15rem)"
      fontWeight: 600
      fontVariationSettings: '"opsz" 48'
      color: "{colors.ink}"
      hover-color: "{colors.accent}"
    tags:
      layout: "flex, gap: 0.35rem, flex-wrap: wrap"
  tag-pill:
    description: >
      Small category or tag chip. Mono text, hairline border or bg-alt fill.
      Used inline in post-index-row and on article pages.
    element: "span.tag-pill"
    fontFamily: '"IBM Plex Mono", "Courier New", monospace'
    fontSize: "0.58rem"
    fontWeight: 500
    letterSpacing: "0.12em"
    textTransform: uppercase
    color: "{colors.ink-faint}"
    border: "1px solid {colors.rule}"
    padding: "0.15em 0.45em"
    background: "transparent (default) or {colors.bg-alt} for active/selected state"
    hoverColor: "{colors.accent}"
    hoverBorder: "1px solid {colors.accent}"
  paper-card:
    description: >
      Card for a published research paper in a listing. Title in Fraunces,
      authors/date in mono, abstract excerpt in Newsreader, prominent link.
    element: "div.paper-card"
    borderTop: "1px solid {colors.rule}"
    padding: "clamp(1.2rem, 2vw, 1.8rem) 0"
    title:
      fontFamily: '"Fraunces", Georgia, "Times New Roman", serif'
      fontSize: "clamp(1.05rem, 1.8vw, 1.4rem)"
      fontWeight: 600
      fontVariationSettings: '"opsz" 48'
      color: "{colors.ink}"
      marginBottom: "0.4rem"
    meta-line:
      font: "{typography.meta}"
      color: "{colors.ink-faint}"
      marginBottom: "0.65rem"
      separator: "· colored {colors.rule}"
    abstract:
      fontFamily: '"Newsreader", Georgia, "Times New Roman", serif'
      fontSize: "clamp(0.88rem, 1.4vw, 1rem)"
      color: "{colors.ink-mid}"
      lineHeight: 1.72
      maxLines: "3–4 lines (use -webkit-line-clamp: 3)"
      marginBottom: "0.75rem"
    link:
      font: "{typography.meta}"
      color: "{colors.accent}"
      borderBottom: "1px solid color-mix(in srgb, var(--accent) 35%, transparent)"
      hover: "border-color: {colors.accent}"
  empty-state:
    description: >
      Minimal error or empty-content pattern. Used for 404 pages, empty archive
      results, or any page where no primary content exists. Centered vertically
      in the main column; copy from [page brief].
    element: "div.empty-state"
    textAlign: center
    paddingTop: "clamp(4rem, 10vw, 8rem)"
    heading:
      font: "{typography.poster}"
      fontSize: "clamp(2.2rem, 5.8vw, 9rem)"
      color: "{colors.accent} (knockout gradient fill, or plain accent — page brief decides)"
      note: "May use the knockout-poster gradient pattern for a single filled line, or plain accent ink."
    body:
      fontFamily: '"Newsreader", Georgia, "Times New Roman", serif'
      fontSize: "clamp(0.95rem, 1.5vw, 1.1rem)"
      color: "{colors.ink-mid}"
      maxWidth: "42ch"
      marginInline: auto
      marginTop: "clamp(1rem, 2vw, 1.5rem)"
    link:
      font: "{typography.meta}"
      color: "{colors.accent}"
      display: "block"
      marginTop: "clamp(1.25rem, 2.5vw, 2rem)"
      letterSpacing: "0.1em"
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
  bullet-list:
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
    description: "Minimal hairline rule + mono stamp line with cosmic accent dots"
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
      note: "Three dots in sequence: accent-blue, accent-violet, accent-pink"
      background: "{colors.accent-blue} / {colors.accent-violet} / {colors.accent-pink} (alternating)"
  theme-system:
    default: "light (:root) — dawn sky / 여명"
    auto: "prefers-color-scheme: dark media query — :root:not([data-theme='light'])"
    manual-dark: "data-theme='dark' on <html>"
    manual-light: "data-theme='light' on <html>"
    storage: "localStorage key: 'esfera-theme'"
    no-fouc: >
      Inline script in <head> before any CSS: reads localStorage and sets
      data-theme on documentElement before first paint. Required on every page.
    toggle-logic: "Reads current state from data-theme or matchMedia fallback; writes opposite; persists to localStorage"
    toggle-icon: "☾ (moon) when light — click to go dark; ☀ (sun) when dark — click to go light"
---

# Esfera Research Design System

## Overview

This DESIGN.md is the reusable **system** (the HOW). It defines tokens, patterns,
and composition rules that apply to every Esfera page. It is always used together
with a **per-page content brief** that supplies copy, intent, and page-specific
decisions (the WHAT). For content pages (posts, lab notes), the markdown content
itself is the page brief. No page copy, file names, or page-specific decisions
live in this document.

Esfera Research is a cosmic scholarly editorial brand with a bold poster opening
available as an optional pattern. The brand operates in two registers that share
one palette:

1. **Scholarly editorial register** — Fraunces display headings, Newsreader
   body text, IBM Plex Mono for labels and metadata. Used on every page except
   when the knockout poster pattern is active.
2. **Knockout poster register** — Archivo Black, huge, uppercase, with 1–2 lines
   on a cosmic gradient fill (blue→violet→pink) with knockout type. Used on pages
   that open with a bold brand statement; typically one such page per site.

Both registers draw from one cosmic palette: one **main accent** (starlight/
periwinkle: `#4a57a6` in light, `#c4cdf0` in dark) and three **cosmic
sub-accents** — blue (`#3a52d6`/`#5b7cff`), violet (`#7a3fd0`/`#9d5cff`),
and pink (`#cf3f86`/`#ff5fa8`). All accents are cool/cosmic — never warm or
amber. (Amber belongs to the separate **Elnath** product brand.)

The sub-accents appear sparingly: sphere strokes, the knockout gradient, small
rules, eyebrow tints, and the footer sig dots. The main accent handles links,
hover states, key rules, and focus outlines.

No shadows exist. Depth is communicated through hairline rules, solid fills
(`--bg-alt`), and the knockout technique. The entire system scales fluidly with
the viewport. The root `font-size` is `clamp(15px, calc(0.45vw + 13px), 22px)`,
every measurement is in `rem`, and the page shell is `min(94vw, 88rem)`. The
page is physically proportional to the viewport at every width, with no
horizontal scroll possible.

---

## Colors

### Light Mode — dawn sky / 여명 (default `:root`)

| Token           | Value      | Role                                                                    |
|-----------------|-----------|-------------------------------------------------------------------------|
| `--bg`          | `#eef0f8` | Page background — pale cool dawn blue-lavender; NEVER warm cream        |
| `--bg-alt`      | `#e4e8f3` | Alternate surface — slightly deeper blue-lavender; callout cards        |
| `--surface`     | `#f7f8fc` | Elevated surface — lightest cool white; reserved for modals/tooltips    |
| `--ink`         | `#181a2b` | Primary text — deep cosmic indigo, not pure black                       |
| `--ink-mid`     | `#51566e` | Secondary text — body prose, nav links                                  |
| `--ink-faint`   | `#888ea6` | Tertiary — labels, metadata, decorative text                            |
| `--rule`        | `#d5d9e8` | Hairline dividers — cool blue-gray                                      |
| `--accent`      | `#4a57a6` | Main — starlight/periwinkle                                             |
| `--accent-blue` | `#3a52d6` | Cosmic blue sub-accent                                                  |
| `--accent-violet`| `#7a3fd0` | Cosmic violet sub-accent                                               |
| `--accent-pink` | `#cf3f86` | Cosmic pink sub-accent                                                  |

### Dark Mode — void / night

| Token           | Value      | Role                                                                    |
|-----------------|-----------|-------------------------------------------------------------------------|
| `--bg`          | `#0a0b12` | Page background — deep void                                             |
| `--bg-alt`      | `#11131d` | Alternate surface — slightly lighter void                               |
| `--surface`     | `#141622` | Elevated surface — lightest dark tone                                   |
| `--ink`         | `#eef1fa` | Primary text — starlight white                                          |
| `--ink-mid`     | `#8c92a8` | Secondary text — muted cosmic lavender                                  |
| `--ink-faint`   | `#4e5364` | Tertiary — very muted space gray                                        |
| `--rule`        | `#20232f` | Hairline dividers — near-invisible dark                                 |
| `--accent`      | `#c4cdf0` | Main — starlight/periwinkle, brighter for contrast on void              |
| `--accent-blue` | `#5b7cff` | Cosmic blue sub-accent dark                                             |
| `--accent-violet`| `#9d5cff` | Cosmic violet sub-accent dark                                          |
| `--accent-pink` | `#ff5fa8` | Cosmic pink sub-accent dark                                             |

### The Accent Story

The Esfera accent system is **one main accent + three cosmic sub-accents**, all
cool and cosmic — never warm. The main accent (`--accent`) is starlight
periwinkle, named for the pale lavender that stars leave on a dark sky. It shifts
between modes to maintain contrast: a deeper indigo-blue in the pale dawn light,
a soft starlight white against the void.

The three sub-accents — blue, violet, and pink — appear only in specific,
intentional roles: the sphere mark strokes, the knockout poster gradient, small
rules/dots/eyebrows, and the footer sig dots. They are not interchangeable with
the main accent; they add cosmic depth at specific focal points.

No warm accent exists in this system. Amber/orange is reserved exclusively for
the **Elnath** product brand and must never appear in Esfera Research UI.

### Theme Switching

Light is the default (`:root`). Dark switches automatically via
`prefers-color-scheme: dark`. A manual toggle overrides this by setting
`data-theme="light"` or `data-theme="dark"` on `<html>` and persisting to
`localStorage` under the key `esfera-theme`. A no-FOUC inline script must appear
in `<head>` before any CSS on every page:

```html
<script>(function(){var t=localStorage.getItem('esfera-theme');if(t)document.documentElement.setAttribute('data-theme',t);})();</script>
```

CSS structure for the token cascade:

```css
/* 1. Light defaults */
:root { --bg: #eef0f8; /* ... all light tokens ... */ }

/* 2. Auto dark (OS dark, no manual override) */
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) { --bg: #0a0b12; /* ... all dark tokens ... */ }
}

/* 3. Manual dark (overrides OS light) */
:root[data-theme="dark"] { --bg: #0a0b12; /* ... all dark tokens ... */ }

/* 4. Manual light (overrides OS dark) */
:root[data-theme="light"] { --bg: #eef0f8; /* ... all light tokens ... */ }
```

The poster hero band inherits `var(--bg)` — it always reflects the current
theme surface, never a forced dark override. Both modes render correctly without
any hero-specific color tokens.

---

## Typography

### Font Stack

Four typefaces. One each for four distinct jobs. No substitution.

| Family | Variable | Use |
|--------|----------|-----|
| Archivo Black | `--f-poster` | Knockout poster headline only |
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
| `--hero-poster` | `clamp(2.2rem, 5.8vw, 9rem)` | Knockout poster — Archivo Black |
| `--hero` | `clamp(2.8rem, 6.2vw, 7.5rem)` | (reserved large display) |
| `--h2-disp` | `clamp(1.35rem, 2.6vw, 2.6rem)` | Display section headings |
| `--pull-q` | `clamp(1.2rem, 2.2vw, 2rem)` | Pull question |
| `--body` | `1rem` | Body prose (inherits fluid root) |
| `--small` | `0.68rem` | Labels, eyebrows, meta |
| post-title | `clamp(2rem, 4.5vw, 4rem)` | Article h1 |
| blockquote | `clamp(1.05rem, 1.8vw, 1.35rem)` | In-article blockquote |

The clamp floor on `--hero-poster` (2.2rem) is a starting point. For any given
page, verify that the longest word in the poster headline fits within the usable
column at 320–390px without horizontal overflow and never auto-hyphenates. Lower
the floor if needed.

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
overflow. There is no cap on body prose width on pages that use the full column
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

This system has no shadows. Depth is communicated by:

1. **Hairlines** — `1px solid var(--rule)` for horizontal rules, rail border,
   card borders, section separators.
2. **Accent rules** — `1px–2.5px solid var(--accent)` (or a sub-accent) for
   pull-quote left rule, callout card top border, title-rule, poster accent bar.
3. **Fill contrast** — `--bg-alt` on callout cards creates depth without shadow.
4. **Knockout type** — the deepest "elevation" effect in the system is the
   knockout poster: a cosmic gradient fill with text cut through it in the page
   surface color. No shadow makes it possible.
5. **Nebula glow** — a faint radial gradient (blue/violet/pink) in the hero
   band adds depth via color rather than shadow or border. Full in dark, barely
   visible in light (dawn-sky wash).

Border-radius is `0` everywhere. Do not introduce radius.

---

## Shapes

### Sphere Mark (brand logomark)

SVG, `1.55rem × 1.55rem`, `fill: none`, `stroke-width: 1.15`, `opacity: 0.9`.
Three paths with cosmic multi-color strokes:

```html
<circle cx="16" cy="16" r="12.5" stroke="var(--accent)"/>
<ellipse cx="16" cy="16" rx="5.2" ry="12.5" stroke="var(--accent-blue)"/>   <!-- meridian -->
<ellipse cx="16" cy="16" rx="12.5" ry="4.6" stroke="var(--accent-violet)"/> <!-- equatorial -->
```

The outer circle uses the main accent; the meridian uses `--accent-blue`; the
equatorial ring uses `--accent-violet`. All three respond to theme switching
automatically via the CSS custom property system.

### Celestial Sphere (hero key visual)

SVG, `clamp(360px, 56vw, 760px)` rendered, `viewBox="0 0 700 700"`. Positioned
absolute at the upper-right focal point of the hero band (`right: -4%, top: -2%`).
Multi-color stroke layers:

```html
<!-- Outer circle: main accent -->
<circle cx="350" cy="350" r="338" stroke="var(--accent)" stroke-width="1.8" opacity="0.45"/>
<!-- Primary meridian: cosmic blue -->
<ellipse cx="350" cy="350" rx="128" ry="338" stroke="var(--accent-blue)" stroke-width="2.0" opacity="0.55"/>
<!-- Equator: cosmic violet -->
<ellipse cx="350" cy="350" rx="338" ry="118" stroke="var(--accent-violet)" stroke-width="2.0" opacity="0.55"/>
<!-- Wide secondary meridian: main accent -->
<ellipse cx="350" cy="350" rx="255" ry="338" stroke="var(--accent)" stroke-width="1.2" opacity="0.28"/>
<!-- Secondary latitude band: main accent -->
<ellipse cx="350" cy="350" rx="338" ry="236" stroke="var(--accent)" stroke-width="1.2" opacity="0.28"/>
<!-- Pink latitude ring: cosmic pink -->
<ellipse cx="350" cy="350" rx="338" ry="58" stroke="var(--accent-pink)" stroke-width="1.4" opacity="0.35"/>
```

All strokes respond to theme automatically. The sphere is always visible in both
modes because the stroke colors are correctly contrasted against both `--bg` values.

### Sig Dots

Three `0.32rem × 0.32rem` circles, `border-radius: 50%`. Colors: `--accent-blue`,
`--accent-violet`, `--accent-pink` in sequence. The only non-zero radius in the
system, and they are decorative only.

---

## Components

### Rail Nav

Sticky left sidebar. Structure from top to bottom:

1. **Brand block** — sphere mark SVG (multi-color strokes) + brand name in `--f-mono`.
2. **Lang + theme row** — lang options + theme toggle in `--f-mono` 0.6rem.
   Active lang in `var(--accent)`. Theme toggle: hover color is `var(--accent)`.
   Toggle shows ☾ in light mode (click → go dark) and ☀ in dark mode (click → go light).
3. **Separator** — `1.5rem` wide, `1px` tall, `var(--rule)`.
4. **Nav links** — Fraunces italic weight-300 `opsz-36`, color `var(--ink-mid)`,
   hover `var(--accent)`.
5. **Spacer** — `flex: 1`.
6. **Stamp** — "Est. 2026" in `--f-mono` uppercase `var(--ink-faint)`.

### Knockout Poster

Used on pages that open with a bold brand statement (typically one such page per
site). This pattern is the sole use of Archivo Black.

The headline consists of 2–4 `span.hl` blocks (`display: block`,
`white-space: nowrap`). Lines designated for knockout fill (per the page brief)
are wrapped in `span.hero-accent-fill`; plain lines are bare `span.hl` in
`var(--ink)`. The number of lines and which receive fill are always determined
by the page brief, not this spec.

**Knockout rule (non-negotiable):**
```css
.hero-accent-fill {
  background: linear-gradient(100deg,
    var(--accent-blue) 0%,
    var(--accent-violet) 55%,
    var(--accent-pink) 100%);
  color: var(--bg);   /* equals the page surface — never black */
  padding: 0.02em 0.1em 0.04em;
  -webkit-box-decoration-break: clone;
  box-decoration-break: clone;
}
```

The letters read as negative space cut through the cosmic gradient fill because
the text color matches the page background. In light mode `var(--bg)` is `#eef0f8`
(dawn pale); in dark mode it is `#0a0b12` (void). The system handles both
automatically.

Gradient values for reference:
- **Dark** (void): `#5b7cff → #9d5cff → #ff5fa8` — vivid cosmic sweep on void
- **Light** (dawn): `#3a52d6 → #7a3fd0 → #cf3f86` — deepened cosmic sweep on pale background

The celestial sphere (upper-right position, `z-index: 0`) and nebula glow
(`::before` pseudo-element) sit behind the headline at `z-index: 0`; all
headline elements are at `z-index: 1`.

Below the headline, `div.hero-lede-wrap` has `border-top: 1px solid var(--rule)`
and contains a single italic paragraph in Newsreader at
`clamp(0.92rem, 1.5vw, 1.1rem)`, color `var(--ink-mid)`, max-width `58ch`.
This lede is optional; include only when the page brief calls for one.

A gradient accent bar (`span.hero-accent-bar`) using
`linear-gradient(90deg, var(--accent-blue) 0%, var(--accent) 40%, var(--accent-violet) 72%, var(--accent-pink) 100%)`
at `opacity: 0.3` separates the poster from the editorial body.

### Nebula Glow

A `::before` pseudo-element on `.hero-band`. Three overlapping radial gradients
in blue/violet/pink hues, clustered at the upper-right where the celestial sphere
sits. Opacity governed by `--nebula-opacity`: `1` in dark (full atmospheric glow),
`0.07` in light (subtle dawn wash). Transitions smoothly on theme switch.

### Starfield

A fixed SVG canvas behind all page content (`z-index: 0`, `pointer-events: none`).
Stars are grouped by tint class (`s-w`, `s-sl`, `s-b`, `s-v`, `s-pk`); CSS
custom properties (`--star-base-*`) drive their fill colors so they respond to
theme automatically. Overall visibility is controlled by `--starfield-opacity`:
`1` in dark (full star field), `0.18` in light (dawn sky — few faint stars,
per the '여명' concept).

Select bright stars carry twinkle animations (`twinkle-a`, `twinkle-b`,
`twinkle-c`). All twinkle animations are suspended under
`@media (prefers-reduced-motion: reduce)`.

### Pull Quote

Left rule in `--accent-violet`, Fraunces italic light, max-width `54ch`.
Emphasis within pull text uses `font-style: normal; font-weight: 600; color: var(--accent)`.

### Callout Card

`--bg-alt` fill. Border: `1px accent-blue top`, `1px rule left/right/bottom`. No
radius. Use for one high-priority callout per section. The landing page's
flagship/Elnath block is the canonical example of this pattern.

### Post Index Row

Archive list row. Three-column grid: mono date (7ch) · Fraunces title (1fr) ·
optional tag pills (auto). Rows separated by `border-bottom: 1px solid var(--rule)`.
Date in `--f-mono` `var(--ink-faint)`. Title in Fraunces semi-bold `opsz 48`,
hover `var(--accent)`. Tags render as `tag-pill` chips.

### Tag Pill

Small category chip. IBM Plex Mono `0.58rem` uppercase `0.12em` letter-spacing,
`var(--ink-faint)`, `border: 1px solid var(--rule)`, `padding: 0.15em 0.45em`.
Active or selected state: `background: var(--bg-alt)`. Hover: `color: var(--accent)`,
`border-color: var(--accent)`.

### Paper Card

For published research paper listings. Sections from top to bottom:

- **Title** — Fraunces semi-bold `clamp(1.05rem, 1.8vw, 1.4rem)` `opsz 48`,
  `var(--ink)`.
- **Meta line** — mono `0.62rem` `var(--ink-faint)`, fields separated by `·`.
  Content from [page brief]: authors, date, venue, tags.
- **Abstract excerpt** — Newsreader `clamp(0.88rem, 1.4vw, 1rem)`,
  `var(--ink-mid)`, line-height `1.72`, clamped to 3–4 lines via
  `-webkit-line-clamp: 3`.
- **Link** — mono `0.62rem` `var(--accent)`, underline via
  `border-bottom: 1px solid color-mix(in srgb, var(--accent) 35%, transparent)`,
  hover brings to full accent.

Separated from adjacent cards by `border-top: 1px solid var(--rule)`.

### Empty State / 404

Minimal pattern for error or empty-content pages. Centered vertically in the
main column. Copy (heading, body, link label) comes from the page brief.

- **Heading** — may use the knockout poster gradient pattern for a single filled
  line, or plain `var(--accent)` ink — page brief decides.
- **Body** — Newsreader `clamp(0.95rem, 1.5vw, 1.1rem)`, `var(--ink-mid)`,
  max-width `42ch`, centered.
- **Link** — mono `var(--accent)`, block-level, `margin-top: clamp(1.25rem, 2.5vw, 2rem)`.

### Section Labels (Eyebrows)

IBM Plex Mono, `0.68rem`, `0.16em` letter-spacing, uppercase, `var(--ink-faint)`.
Used as `h2.label` above display headings. An optional tint variant (`color: var(--accent-blue); opacity: 0.75`) may be used on sections that semantically relate to the cosmic blue sub-accent. Never replace with a serif.

### Display Headings

Fraunces semi-bold, `clamp(1.35rem, 2.6vw, 2.6rem)`, `opsz 48`,
letter-spacing `-0.018em`, line-height `1.2`, `var(--ink)`.

### Principles List

Ruled list: each `<li>` has `padding: 0.85rem 0`, `border-bottom: 1px solid var(--rule)`. First item also has `border-top`. Bold terms inside use Fraunces
semi-bold weight-600, inline, `var(--ink)`.

### Bullet List

Em-dash bullets. The `::before` pseudo-element renders `"—"` in
`var(--accent)`, Fraunces weight-300. Content `padding-left: 1.4rem`.

### Article Layout

Rail identical to all other pages. Main column:
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
- **ul** — em-dash bullets, same as bullet list.
- **Links** — `color: var(--accent)`,
  `border-bottom: 1px solid color-mix(in srgb, var(--accent) 35%, transparent)`,
  hover brings border to full accent.
- **hr.section-rule** — `1px solid var(--rule)`, margin `clamp(1.8rem, 3.5vw, 3rem) 0`.
- **Post signature** — Newsreader italic `var(--ink-faint)`.

### Footer

A horizontal hairline rule (`1px solid var(--rule)`) followed by a mono stamp
line. The stamp is `0.62rem` uppercase `0.08em` letter-spacing `var(--ink-faint)`,
preceded by three `0.32rem` cosmic dots in `--accent-blue`, `--accent-violet`,
and `--accent-pink` in sequence.

---

## Do's and Don'ts

### Do's

- **Do use `var(--accent)` for the primary accent need** — the sphere mark outer
  stroke, key rules, title rules, bullet em-dashes, link colors, hover states,
  focus outlines. Reserve sub-accents for their specific roles.
- **Do use sub-accents only in their designated roles** — `--accent-blue` for
  the sphere meridian, callout card top border, and blue-tinted eyebrows;
  `--accent-violet` for the sphere equator and pull-quote left rule; `--accent-pink`
  for the sphere latitude ring, sig dots, and gradient endpoints. Never randomly
  swap sub-accents.
- **Do use the gradient (blue→violet→pink) for the knockout poster fill** — not
  a flat accent, not a single color. Both light and dark gradient values are
  specified; use the CSS custom property tokens so theme switching is automatic.
- **Do write every measurement in `rem`** — even `0.32rem` for the sig dots.
  Nothing in `px` after the root font-size declaration.
- **Do apply `min-width: 0` to all grid children** — this is what prevents
  grid items from overflowing their track.
- **Do include the no-FOUC script in `<head>` before any `<link rel="stylesheet">`
  or `<style>` on every page.**
- **Do set `hyphens: none; overflow-wrap: normal; word-break: normal` on the
  poster headline** — the clamp already prevents overflow; browser auto-hyphenation
  would break any long word mid-word.
- **Do use `white-space: nowrap` on each `.hl` span** — poster headline lines
  are editorially fixed; they must never reflow.
- **Do use `overflow: hidden` on `.hero-band`** — the celestial sphere extends
  beyond the hero area and must be clipped.
- **Do apply `prefers-color-scheme` with the `:root:not([data-theme="light"])`
  guard** — this lets the manual toggle override OS preference without fighting
  the media query.
- **Do use `opsz` variation settings on Fraunces** — the font is a variable face;
  optical sizing at the rendered size is part of the type system.
- **Do respect `prefers-reduced-motion`** — suspend all twinkle animations on
  the starfield under `@media (prefers-reduced-motion: reduce)`.

### Don'ts

- **Don't put black (or `var(--ink)`) text on the knockout gradient fill** — the
  knockout text on `hero-accent-fill` must be `color: var(--bg)` (the page
  surface color). In light mode `#eef0f8`; in dark mode `#0a0b12`. If it is black,
  the "cut-out" reading is lost. This is the single most important rule in the system.
- **Don't use a flat accent color for the knockout fill** — the knockout poster
  uses a gradient (blue→violet→pink), not a single `--accent` block. The gradient
  is what makes the cosmic character.
- **Don't introduce a warm accent** — not amber, not orange, not any warm hue.
  All accents are cool/cosmic. Amber belongs exclusively to the Elnath product
  brand and must not appear in Esfera Research UI.
- **Don't add a fourth accent color** — the system has one main accent and three
  sub-accents. Adding a fourth disrupts the intentional palette.
- **Don't let any element cause horizontal scroll** — enforce `overflow-x: hidden`
  on `html`, `body`, and `.main`; `min-width: 0` on `.main` and all grid
  children; `max-width: 100%` on the poster headline. Test at 320px.
- **Don't use Archivo Black anywhere except the knockout poster** — it is a display
  face with one weight and no optical sizes. Fraunces handles all other display
  needs.
- **Don't force a specific poster background** — the poster uses `var(--bg)`,
  not a fixed background. In light mode the poster is dawn blue-lavender. In dark
  mode it is void. The same markup works for both.
- **Don't use `px` for layout measurements** — the fluid scaling system only
  works if spacing, type, and layout are in `rem` relative to the fluid root
  font-size.
- **Don't add `border-radius`** — except the `50%` sig dots, which are decorative
  and not UI elements. All interactive elements (buttons, cards, inputs) are
  sharp-cornered.
- **Don't add shadows** — not `box-shadow`, not `drop-shadow`, not `text-shadow`.
  Depth comes from hairlines, fill contrast, and the nebula glow.
- **Don't hyphenate any word in the poster headline** — the `hyphens: none` rule
  is mandatory on `.hero-headline`. If a word causes overflow at a narrow viewport,
  lower the clamp floor of `--hero-poster` rather than allowing a hyphen.
- **Don't override `font-size` on `html`** — the single `clamp()` declaration
  governs the whole scale. A local override on `html` breaks the fluid system.
- **Don't add a second display font** — Fraunces is the display face for all
  non-poster headings. A second display font would fragment the editorial register.
- **Don't use `overflow: visible` on `hero-band`** — the celestial sphere will
  bleed into adjacent sections.
- **Don't use hardcoded light or dark hex values in component CSS** — always
  reference a token (`var(--bg)`, `var(--ink-mid)`, `var(--accent-blue)`, etc.)
  so theme switching works automatically.
- **Don't disable or skip the starfield's `prefers-reduced-motion` guard** — the
  twinkle animations must be suspended for users with motion sensitivity.

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

### Testing Checklist

- No horizontal scrollbar at `320px`.
- Poster headline stays on its designed line count at all widths.
- The longest word in the poster headline never hyphenates and never causes
  horizontal overflow at 320–390px.
- Theme toggle shows correct icon in both modes (☾ in light, ☀ in dark).
- No FOUC on page load.
- Rail collapses correctly at `720px`.
- Focus outlines visible (`1px solid var(--accent), offset 3px`) in both themes.
- Starfield is faint/dawn in light mode (`--starfield-opacity: 0.18`); full in dark mode.
- Nebula glow is subtle in light mode (`--nebula-opacity: 0.07`); full in dark mode.
- All twinkle animations paused under `prefers-reduced-motion: reduce`.

---

## Page-Type Kit

Reference table for composing any page type in this system. "Hero?" refers to
the knockout-poster pattern. Use the page brief for all copy and intent.

| Page type    | Hero?    | Main components                                                         | Prose max   |
|-------------|---------|-------------------------------------------------------------------------|-------------|
| Landing     | Yes      | knockout-poster · pull-quote · callout-card · bullet-list · section-label | none       |
| Blog post   | No       | article-layout (post-meta · h1 · title-rule · body · blockquote · ul)  | 66ch        |
| Paper list  | No       | section-label · post-index-row or paper-card · tag-pill                 | none        |
| About       | Optional | display-heading · principles-list · bullet-list · callout-card          | none / 66ch |
| 404 / empty | Optional | empty-state (heading · body · link)                                     | 42ch        |

---

## Iteration Guide — Designing Any Page

Steps an AI design agent follows to compose any new Esfera page using this system
and a page brief:

1. **Read the page brief** — understand the page's purpose, content, and any
   page-specific decisions (hero?, line count, which lines get fill, lede text).
   Consult the Page-Type Kit table above to identify the standard component set.

2. **Copy the no-FOUC script** into `<head>` before any `<style>` or `<link>`.

3. **Load all four fonts** via the Google Fonts URL string specified in the
   Typography section.

4. **Paste the full token block** — light defaults on `:root`, auto-dark via
   `@media (prefers-color-scheme: dark){ :root:not([data-theme="light"]){...} }`,
   manual dark via `:root[data-theme="dark"]`, and manual light override via
   `:root[data-theme="light"]`.

5. **Set root font-size** on `html`:
   `font-size: clamp(15px, calc(0.45vw + 13px), 22px)`.

6. **Set overflow guards** on `html` (`overflow-x: hidden`), `body`
   (`overflow-x: hidden; max-width: 100%`), and `.main`
   (`min-width: 0; max-width: 100%; overflow-x: hidden`).

7. **Build the shell** as a 2-column CSS Grid with the rail at `var(--rail-w)`
   and the main column as `1fr`. Copy the `≤720px` breakpoint collapse.

8. **Build the rail** as a sticky sidebar with the sphere mark SVG (three
   multi-color strokes), brand name, lang row, theme toggle, separator, nav
   links, spacer, and stamp. Copy the theme toggle script verbatim.

9. **Add the starfield SVG** as a fixed background element (`#starfield`).
   Ensure star classes (`s-w`, `s-sl`, `s-b`, `s-v`, `s-pk`) are present so
   CSS custom properties drive their fills. Set `--starfield-opacity` and
   `--nebula-opacity` for both theme states. Add
   `@media (prefers-reduced-motion: reduce)` to suspend twinkle animations.

10. **Decide: does this page have a knockout poster?** Consult the page brief and
    the Page-Type Kit.
    - If yes: add `section.hero-band` with the `::before` nebula glow, the
      celestial sphere SVG, eyebrow, an `h1.hero-headline` with the line count
      and fill assignment from the page brief, an optional lede-wrap paragraph,
      and the gradient `span.hero-accent-bar`. Verify the clamp floor against
      the longest word.
    - If no: begin main content with padding `var(--pad-top) var(--pad-side)`.

11. **Assemble the main content area** using the components specified for this
    page type in the Page-Type Kit. All copy comes from the page brief.

12. **For article/post pages**: wrap content in `article.post` with
    `max-width: 66ch`. Include post-meta, `h1.post-title`, `hr.title-rule`
    (2.5px accent, 3.5rem wide), then body prose.

13. **For index/archive pages**: use `post-index-row` or `paper-card` for each
    entry; add `tag-pill` chips as appropriate.

14. **For empty/error pages**: use the `empty-state` pattern. Follow the page
    brief for whether to invoke the knockout poster gradient or plain accent heading.

15. **Place the footer**: `hr.foot-rule` + `.sig` with three cosmic dots
    (blue/violet/pink) and mono text.

16. **Check all colors reference tokens**, not hardcoded hex values.

17. **Verify the checklist** in the Responsive Behavior section before shipping.

---

## Known Gaps

The following content primitives exist in the research/product roadmap but are
not yet fully specified in this system:

- **Citation rows** — Inline or footnote citations referencing prior work.
  Format, numbering style, and hover/expand behavior are undefined.

- **Failure log / graveyard timeline** — A chronological list of dead
  experiments. Design questions open: timeline spine treatment (vertical rule?
  cosmic dots?), how "dead" is communicated visually (faint ink? strikethrough?),
  whether entries have expandable detail or are permanently collapsed.

- **Dataset listings** — Cards or rows for public datasets released or used by
  the lab. License badges, size, format, and download link treatment are not
  yet designed.

- **Localization register** — The Korean register uses the same token system and
  layout, but the poster headline uses `word-break: keep-all`. Full Korean
  typography review (line-height, Fraunces in Hangul fallback) is pending.
