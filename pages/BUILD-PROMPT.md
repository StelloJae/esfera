# Build prompt — for web Claude (claude.ai)

Use this to have claude.ai build Esfera pages from the design system. **Workflow:** paste the prompt below **+ the full `DESIGN.md` + one page brief**, get one HTML file back, repeat per page (reuse the same prompt + DESIGN.md, swap the brief).

- DESIGN.md (raw): https://raw.githubusercontent.com/StelloJae/esfera/main/DESIGN.md
- A page brief: e.g. https://raw.githubusercontent.com/StelloJae/esfera/main/pages/landing.brief.md
- Content pages (posts/lab notes): the markdown content itself IS the brief.

---

## Prompt (copy from here)

You are building pages for the **Esfera Research** website — a static, fluid, light/dark site.

You work from TWO inputs I provide:
1. A **DESIGN SYSTEM** (`DESIGN.md`) — the complete styling system: tokens, component patterns, rules. It is the ONLY source of styling. Follow it exactly.
2. A **PAGE BRIEF** — the content + which components for one specific page (the WHAT). For posts/lab notes, the brief is just the markdown content.

OUTPUT, per page: ONE self-contained static HTML file.
- All CSS inline in a single `<style>`. No build step, no frameworks, no external CSS file.
- Google Fonts via `<link>` only (Fraunces, Newsreader, IBM Plex Mono, Archivo Black). No other external resources.
- Must work as a plain `.html` on GitHub Pages.

NON-NEGOTIABLE RULES (don't violate, even if you skim the system):
- **ONE warm accent only** (the amber tokens). Never add a second accent color.
- **Fluid & proportional**: root `font-size: clamp(15px, calc(0.45vw + 13px), 22px)`; size everything in `rem`; shell `width: min(94vw, 88rem)`. The page scales with the window.
- **ZERO horizontal scroll at any width** (`overflow-x:hidden` on html/body/.main, `min-width:0` on grid children, hero type sized so its longest word fits ~320px without overflow, `hyphens:none` on the hero).
- **Light + dark**: auto via `prefers-color-scheme` PLUS a manual ☀/☾ toggle (`data-theme` override + `localStorage` + the no-FOUC inline script in `<head>` before CSS).
- **Knockout-poster hero** (only if the brief specifies one): accent-filled words have `color: var(--bg)` (the surface color) so letters read cut-out — NEVER black.
- **Archivo Black ONLY for the poster hero.** Body = Fraunces (display) + Newsreader (reading) + IBM Plex Mono (labels).
- No shadows/gradients; depth via hairlines + color. Minimal / 0 radius.
- Accessible: semantic HTML, strong contrast, `aria-hidden` on the decorative sphere mark.

Build the page the brief describes by composing the components defined in `DESIGN.md`. If the brief is missing something you need, ask; otherwise output the complete HTML file.

— end of prompt —

---

Then paste, in the same message:

```
====== DESIGN SYSTEM ======
[paste full DESIGN.md]

====== PAGE BRIEF ======
[paste the page brief, e.g. pages/landing.brief.md]
```
