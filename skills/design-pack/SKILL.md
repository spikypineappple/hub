---
name: design-pack
description: >-
  The Design Pack — the default design system for ANY website-style asset. Bundles
  Impeccable (craft/anti-slop), Kowalski/emil-design-eng (motion), and taste-skill
  (dials + AI-tell bans) into one pass, plus Banana for custom graphics and a
  bespoke animated signature graphic. USE THIS BY DEFAULT whenever creating,
  designing, building, redesigning, or polishing a website, landing page, marketing
  page, site, hero, section, HTML/CSS page, React/Vue/Svelte UI, component, dashboard,
  brand page, or any web/UI visual asset. Triggers on: "website", "landing page",
  "site", "web page", "UI", "hero", "redesign", "build a page/component", ".html/.tsx".
  If a task will produce a web-style visual asset, run Design Pack first.
---

# Design Pack — the combined web-asset design pass

One skill, three disciplines, run together on every website-style asset. Do not
ship a web asset that skipped this. Load the three source skills when you need
their full detail (`impeccable`, `emil-design-eng`, `taste-skill`); the essentials
are inlined below so this is self-sufficient.

## The order of operations

1. **Frame it (Impeccable).** Decide register (brand vs product), theme (write the
   one-sentence physical scene, don't default), and a committed **color strategy**
   (restrained / committed / full-palette / drenched — not always "one accent"). Pick
   a distinctive type system (never the reflex: no Inter-for-premium, no Fraunces-as-
   default-editorial). Run the **AI-slop test** at two altitudes: if the palette/type
   is guessable from the category, or from category+anti-reference, rework it.

2. **Commission the graphics (Banana).** Custom imagery over stock, always. Invoke the
   `banana` skill to generate logos, hero images, textures, and brand stills. Prefer
   the subject's **real** photography when it exists; otherwise generate
   locality/context-accurate images, never generic stock. Face-free, editorial,
   consistent grade. Cost discipline: paid image credits need the owner's go.

3. **Give it a signature graphic.** Every asset carries ONE bespoke visual centerpiece,
   native to its concept — not a shared template widget. **If the brief suits it, build
   an animated diagram**: a node/network graph (nodes + connecting edges + travelling
   current/pulses), or the concept-appropriate equivalent — radar/sweep, energy-flow,
   timeline, orbit, coverage map. SVG + CSS/SMIL, `prefers-reduced-motion` safe. Two
   assets must never share the same signature graphic.

4. **Apply the motion + texture layer (Kowalski + Taste).** This is the craft floor —
   apply it by default (see the drop-in below).

5. **Pre-flight.** Run the checklist at the bottom before you call it done.

## Motion (Kowalski / emil-design-eng — the non-negotiables)

- **Strong custom easing, never the weak built-ins.**
  `--e-out:cubic-bezier(0.16,1,0.3,1)` · `--e-emil:cubic-bezier(0.23,1,0.32,1)`.
  Entrances/exits = ease-out. Never `ease-in` on UI. Never `transition: all`.
- **Only animate `transform` and `opacity`** (GPU). Never `width/height/top/left`.
- **Never `scale(0)`** — start `scale(0.95)` + `opacity:0` + optional `blur`.
- **`:active` feedback** on every pressable: `transform: scale(0.97)`.
- **Stagger** grouped entrances 30–110ms; keep UI motion <300ms (marketing can be longer).
- **Scroll reveals** via IntersectionObserver (`{once}`), not scroll listeners.
- **Springs** for drag/alive elements; **reduced-motion** = fewer/gentler, keep opacity.
- Purpose test: if it's seen 100+×/day, don't animate it. Marketing hero = delight OK.

## Texture + dials (taste-skill)

- Baseline dials: **VARIANCE 8, MOTION 6, DENSITY 4** (adapt to the brief).
- **Grain/noise** as a fixed `pointer-events-none` overlay (never on a scroll container),
  `mix-blend-mode: multiply` (light) or `soft-light` (dark). Flat color fields read as slop.
- **Magnetic** buttons (cursor pull, transform only) and **cursor-spotlight** cards
  (`radial-gradient at var(--mx)/var(--my)`) with tinted-shadow hover lift.
- Anti-center bias; asymmetry; cards only when elevation earns it.
- **AI-tell bans:** no pure `#000`/`#fff`; no neon/outer glows (use inner borders / tinted
  shadows); no gradient-filled headline text; no "Lila" purple-blue AI aesthetic; no Inter;
  no generic 3-equal-card row; no em dashes; no emoji (use SVG/icons); no fake round numbers
  or "John Doe" names; no Unsplash.

## The drop-in motion+texture layer (static HTML / any stack)

```css
:root{--e-out:cubic-bezier(0.16,1,0.3,1);--e-emil:cubic-bezier(0.23,1,0.32,1)}
.grain{position:fixed;inset:0;z-index:60;pointer-events:none;opacity:.4;mix-blend-mode:multiply; /* soft-light on dark */
  background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='140' height='140'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='2' stitchTiles='stitch'/><feColorMatrix type='saturate' values='0'/></filter><rect width='100%25' height='100%25' filter='url(%23n)' opacity='0.5'/></svg>")}
[data-reveal]{opacity:0;transform:translateY(18px);filter:blur(6px);transition:opacity .8s var(--e-out),transform .8s var(--e-out),filter .8s var(--e-out)}
[data-reveal].in{opacity:1;transform:none;filter:none}
@media(prefers-reduced-motion:reduce){[data-reveal]{opacity:1;transform:none;filter:none;transition:none}}
.btn:active{transform:scale(.97)}
```

```js
// reveal on scroll (stagger via inline transition-delay), magnetic buttons, spotlight cards.
// IntersectionObserver {threshold:.14, rootMargin:'0px 0px -7% 0px'}, unobserve on reveal.
// Respect prefers-reduced-motion (force .in, skip magnetic/spotlight).
```

For React/Motion: `useInView({once})`, `useSpring`/`useMotionValue` for magnetic (outside
render), CSS animations for predetermined/perpetual motion (off main thread), Motion for
interruptible/gesture. Never mix GSAP/Three with Motion in one tree.

## When generating MANY sites (build-in-bulk)

Structural sameness across sites is real harm (Google duplicate penalty + "that's me"
collapse). Each site must be a different **concept** (different information architecture +
copy + signature graphic), matched to the business's real character — not one template
reskinned. Gate on real IA+copy overlap, target **<10% shared spine** vs every prior site.

## Pre-flight checklist

- [ ] Register/theme/color-strategy chosen deliberately; passes the two-altitude AI-slop test.
- [ ] Custom graphics via Banana (real photo first); no stock, no generic AI-people in UI.
- [ ] One bespoke signature graphic; animated diagram if the brief suits it; not reused.
- [ ] Motion: custom easing, transform/opacity only, `:active`, stagger, scroll-reveal, reduced-motion.
- [ ] Texture: grain overlay + tinted shadows; no flat slop; no AI-tells; no em dashes/emoji.
- [ ] Copy concrete and in-voice (run `humanizer` on user-facing copy); real numbers only.
