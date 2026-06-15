# D-a — Design Spec
**Direction:** Signal (D) variant — electric cyan-azure accent, fluid scaling

---

## Relation to D / Signal

D-a is a direct variation of the Signal (D) direction. It preserves every structural decision from D exactly:
- Pure black canvas `#000`
- Archivo Black as the sole display face, massive all-caps
- Space Mono for all labels, body, and navigation
- Accent used exclusively as **solid fill** (never stroke, glow, gradient, or text-on-dark)
- One fill moment per section maximum
- `0px` border radius everywhere
- No shadows, no gradients, no decorative art beyond the sphere mark

The two changes are: (1) accent color, and (2) fluid scaling system.

---

## Color Tokens

| Token | Hex | Role |
|---|---|---|
| `--black` | `#000000` | Canvas, nav bg, page background |
| `--white` | `#ffffff` | Primary text, headlines |
| `--off` | `#111111` | Alternate dark surface |
| `--mid` | `#2a2a2a` | Section rule backgrounds |
| `--dim` | `#5a5a5a` | Section labels, eyebrows |
| `--accent` | **`#1fd8ff`** | **Solid fill only** — hero headline block, pullquote keyword, flagship header band, sphere mark, dot |
| `--accent-dim` | `#032833` | Reserved for future accent-on-dark surfaces |

**Accent: `#1fd8ff` — electric cyan-azure.**
Chosen to be noticeably more saturated and more blue than D's mint `#3cffd0`. At this hue (~196° on the color wheel) it reads as "cool-tech" and "electric" — closer to Hermes's dark-web energy — while preserving the stark contrast on black that the solid-fill rule demands.

**Accent-as-Fill Rule** (inherited from D): `#1fd8ff` is applied only as `background: #1fd8ff; color: #000`. Never as a text color on dark, never as a border, never as a gradient stop.

---

## Type Tokens

| Role | Family | Size (fluid) | Weight | Transform | Tracking |
|---|---|---|---|---|---|
| Display / Hero | Archivo Black | `clamp(3rem, 9vw, 11rem)` | 900 | UPPERCASE | `-0.02em` |
| Sub-headline | Archivo Black | `clamp(1.6rem, 4.5vw, 4rem)` | 900 | UPPERCASE | `-0.01em` |
| Section title | Archivo Black | `clamp(1.8rem, 4vw, 3.6rem)` | 900 | UPPERCASE | `-0.01em` |
| Principle label | Archivo Black | `clamp(0.85rem, 1.5vw, 1.25rem)` | 900 | UPPERCASE | `-0.01em` |
| Flagship title | Archivo Black | `clamp(2.2rem, 6vw, 6rem)` | 900 | UPPERCASE | `-0.02em` |
| Body / lede | Space Mono | `clamp(0.75rem, 1.2vw, 0.9rem)` | 400 | none | 0 |
| Eyebrow / label | Space Mono | `clamp(0.5rem, 0.85vw, 0.65rem)` | 700 | UPPERCASE | `0.2em` |
| Nav links | Space Mono | `clamp(0.5rem, 0.85vw, 0.65rem)` | 400 | UPPERCASE | `0.12em` |

All px values are relative to the fluid root font-size (see below) — they grow proportionally with viewport width.

---

## Responsive — Fluid Scaling

D-a replaces D's fixed-`px` layout with the same fluid system used in `design-lab/fluid/`.

**Root font-size:**
```css
html { font-size: clamp(15px, calc(0.45vw + 13px), 22px); }
```
~15px at 360px viewport → ~22px at ~1700px viewport. All `rem`/`em` values in the page scale automatically with it — no breakpoint jumps for type or spacing.

**Shell:**
```css
.shell { width: min(94vw, 88rem); margin-inline: auto; }
```
Wide screens are used fully; dead side margins are eliminated.

**Side padding:**
```css
--pad-side: clamp(1.25rem, 3.5vw, 2.8rem);
```

**Vertical section padding:**
```css
--pad-v:    clamp(4rem, 7vw, 8rem);    /* major sections */
--pad-v-sm: clamp(2.5rem, 5vw, 5.5rem); /* tighter sections */
```

**Column gaps:**
```css
--gap-col:    clamp(2rem, 4vw, 5rem);
--gap-col-sm: clamp(1.25rem, 2.5vw, 3rem);
```

Dark-only — no light mode. The black canvas is load-bearing to the poster aesthetic.

---

## Breakpoints (structural only)

| Breakpoint | Change |
|---|---|
| `≤ 900px` | 2-col layouts collapse to 1-col; hero meta hidden |
| `≤ 600px` | Nav links hidden; principles grid collapses to 1-col |

---

## Do / Don't (inherited from D, accent updated)

**Do:**
1. Use `#1fd8ff` as a single solid fill block per section — one moment, never two
2. Let massive Archivo Black do the decorative work; whitespace is the structural reset
3. Keep body copy Space Mono at muted grays (`#888–#c0c0c0`); only key highlights go `#fff`
4. Size everything in `rem`/`em` so it scales with the fluid root

**Don't:**
1. Use the accent as a border, text color on black, or gradient stop
2. Round any corners — `0px` radius is non-negotiable
3. Introduce a second accent or warm tones
4. Revert any dimension to a fixed `px` value (breaks fluid scaling)
5. Add a light mode — D-a is a black poster, dark-only by design
