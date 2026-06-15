# Page briefs — the WHAT

Esfera's design is **two layers**:

- **`/DESIGN.md`** = the reusable design **system** (the HOW — tokens, components, rules). It is page-agnostic and rarely changes.
- **`/pages/*.brief.md`** = a per-page **content brief** (the WHAT — copy, intent, which components). One per *structural* page.

An AI builds a page by reading **DESIGN.md + that page's brief together**.

## Important
- A brief is **light**: content + intent + which components to use. **No CSS, no colors, no sizes, no fonts** — styling lives only in DESIGN.md. (Re-specifying style here re-creates the over-fit problem.)
- **Content pages (posts, lab notes, papers) don't need a brief** — the markdown content itself (e.g. `/posts/*.md`) IS the page brief; the system renders it with `article-layout`.
- Only **structural pages** (landing, about, 404, paper-list index) get a brief here.

## Template

```
# Page brief — <name>

- Page type: landing | blog post | paper list | about | 404   (see DESIGN.md → Page-type kit)
- Path: /...   (note KO mirror if any)

## Hero (only if the page uses the knockout-poster)
- Lines (2–4, each its own line; mark plain or FILL):
  - "<text>"  — plain
  - "<text>"  — FILL
- Lede (optional, one italic sentence): "<text>"
- Sphere watermark: yes | no

## Body (in order; pick components from DESIGN.md)
1. <component> — <content / intent>
2. ...

## Nav / links
- <rail nav links, language toggle, etc.>

## Notes
- <any page-specific emphasis or intent>
```
