# Build prompt — for web Claude (claude.ai)

Use this to have claude.ai build Esfera pages from the design system. **Workflow:** paste the prompt below **+ the full `DESIGN.md` + one page brief**, get one HTML file back, repeat per page (reuse the same prompt + DESIGN.md, swap the brief).

- DESIGN.md (raw): https://raw.githubusercontent.com/StelloJae/esfera/main/DESIGN.md
- A page brief: e.g. https://raw.githubusercontent.com/StelloJae/esfera/main/pages/landing.brief.md
- Content pages (posts/lab notes): the markdown content itself IS the brief.

## How to use on claude.ai (verified, June 2026)

claude.ai builds pages as **Artifacts** — live HTML that renders in a side panel and can be shared via a claude.ai link (viewers need no account). One page = one artifact. Two ways to supply the design system:

**A. One-shot (most reliable).** In a normal chat, paste the prompt below **+ the full DESIGN.md + the page brief in ONE message** → you get an HTML artifact. The whole system stays in-context, so no rule is missed. Re-paste per page (tedious but faithful).

**B. A Project (convenient for many pages).** Create a Claude **Project** → put the prompt below (+ the NON-NEGOTIABLE rules) in the Project's **custom instructions**, and upload DESIGN.md to **Project knowledge**. Then each chat = just a page brief → an artifact.
- ⚠️ Project knowledge is retrieved via **RAG** — it may not surface every design rule for every request. Keep the non-negotiable rules in the **custom instructions** (always in-context) and **eyeball each artifact** against them.
- ⚠️ Upload DESIGN.md as **`.txt` or `.html`** (Projects accept TXT/HTML, not MD) — or just paste it.

Recommendation: **B** for convenience, with the non-negotiables in custom instructions + a quick visual check of each page.

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
- **Cosmic accents only**: ONE main (starlight `#c4cdf0` dark / periwinkle `#4a57a6` light) + up to THREE cool subs — blue/violet/pink. NEVER warm/amber (that palette belongs to Elnath, not Esfera). Background is **void** in dark (`#0a0b12`) / **dawn-sky pale** in light (`#eef0f8`) — never cream.
- **Fluid & proportional**: root `font-size: clamp(15px, calc(0.45vw + 13px), 22px)`; size everything in `rem`; shell `width: min(94vw, 88rem)`. The page scales with the window.
- **ZERO horizontal scroll at any width** (`overflow-x:hidden` on html/body/.main, `min-width:0` on grid children, hero type sized so its longest word fits ~320px without overflow, `hyphens:none` on the hero).
- **Light + dark**: auto via `prefers-color-scheme` PLUS a manual ☀/☾ toggle (`data-theme` override + `localStorage` + the no-FOUC inline script in `<head>` before CSS).
- **Knockout-poster hero** (only if the brief specifies one): accent-filled words sit on a **blue→violet→pink gradient fill** with `color: var(--bg)` so letters read cut-out — NEVER black. Hero key visual = a wireframe **celestial sphere** (multi-color strokes) + faint **nebula glow** + theme-aware **starfield** (full in dark, few/faint in dawn).
- **Archivo Black ONLY for the poster hero.** Body = Fraunces (display) + Newsreader (reading) + IBM Plex Mono (labels).
- No shadows; depth via hairlines + color. Minimal / 0 radius. The ONLY gradient is the knockout nebula sweep + the faint hero nebula glow.
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
