# Aesthetic recipes: concrete kits for a committed direction

`design-vocabulary.md` names ~22 directions in the abstract. This file is the
opposite end: once you have committed to one direction, here is the concrete
kit (fonts, palette, radius, components, motion) so the build stays coherent and
does not drift back to defaults. Pull in only the recipe you are building.

These are starting points to push fully, not menus to mix. A half-committed
direction reads as generated. Pick one, commit, and let one sharp contrasting
accent carry the surprise.

---

## Minimalist / editorial (Notion / Linear vibes)

The point is precision in spacing and type, not absence of design. A pure-text
page is incomplete work, not minimalism (still needs 2-3 real images).

- **Type:** clean geometric sans for body/UI (Geist, Switzer, SF Pro-like). If a
  display serif is genuinely earned, a distinctive modern one (not Fraunces /
  Instrument Serif). Tight tracking on display (`-0.02em` to `-0.04em`),
  line-height 1.6 on body, max-width 65ch. Mono for data/keystrokes.
- **Color:** warm monochrome canvas (`#FFFFFF` or bone `#F7F6F3`), off-black text
  (`#111` / `#2F3437`, never pure black), ultra-light dividers (`#EAEAEA` /
  `rgba(0,0,0,.06)`). Accents are washed-out pastels used only for tags or inline
  code, never large fields or gradients.
- **Shape:** crisp radius (8-12px max), no `rounded-full` on large containers,
  shadows near-invisible (opacity < 0.05) or absent.
- **Components:** bento grids with `1px solid #EAEAEA` borders and generous
  padding (24-40px); accordions stripped to a `border-bottom` + a sharp `+`/`-`;
  keystrokes as real `<kbd>` chips; faux-OS chrome with three light-grey dots.
- **Motion:** invisible. Scroll-entry fade + 12px rise over ~600ms, hover lift to
  a 2px/0.04-opacity shadow, staggered reveals. IntersectionObserver, never a
  scroll listener.
- **Macro-whitespace first:** `py-24`/`py-32` sections, content `max-w-4xl/5xl`.

## Brutalist / industrial (Swiss print x tactical terminal)

Raw, mechanical, high-density. Pick ONE substrate and commit; never mix the two
modes in one interface.

- **Swiss Industrial (light):** unbleached-paper bg (`#F4F4F0` / `#EAE8E3`),
  carbon ink fg (`#050505`-`#111`), single hazard-red accent (`#E61919` /
  `#FF2A2A`) for strike-throughs, structural rules, vital data.
- **Tactical Telemetry (dark):** deactivated-CRT bg (`#0A0A0A` / `#121212`, never
  pure black), white-phosphor fg (`#EAEAEA`), same hazard red. Terminal green
  (`#4AF626`) only for a single status element, or omit.
- **Type:** macro headers in heavy neo-grotesque (Archivo Black, Monument
  Extended, Inter Black) at `clamp(4rem, 10vw, 15rem)`, tracking `-0.03em` to
  `-0.06em`, leading `0.85`-`0.95`, all-caps. Micro/data in mono (JetBrains Mono,
  IBM Plex Mono, Space Mono) at 10-14px, tracking `0.05em`-`0.1em`, all-caps.
- **Layout:** strict blueprint CSS Grid, visible compartmentalisation with
  `1px`/`2px` solid borders, full-width `<hr>` dividers, bimodal density (packed
  mono clusters vs vast negative space). Absolute rejection of border-radius:
  every corner 90 degrees.
- **Symbology:** ASCII framing (`[ DELIVERY ]`, `>>>`, `///`), registration marks
  (`®`/`™`) as structural geometry, crosshairs at grid intersections, randomised
  unit strings (`REV 2.6`, `UNIT / D-01`).
- **Texture:** halftone / 1-bit dithering on images and large serifs, CRT
  scanlines via `repeating-linear-gradient`, a global low-opacity noise filter.
- **Grid trick:** `display: grid; gap: 1px` with contrasting parent/child
  backgrounds gives razor-thin dividers without border declarations. Semantic
  tags (`<data>`, `<samp>`, `<kbd>`, `<output>`, `<dl>`).

## Soft / premium agency ($150k-build feel)

Apple/Linear-tier polish: haptic depth, cinematic spatial rhythm, spring motion.
Never repeat the same layout twice; rotate vibe + layout archetypes.

- **Banned outright here:** Inter / Roboto / Arial / system fonts; thick Lucide /
  FontAwesome / Material icons (use Phosphor Light, Remix Line); generic 1px grey
  borders and harsh dark drop-shadows; edge-to-edge sticky navbars; `linear` /
  `ease-in-out` transitions.
- **Vibe archetypes (pick 1):** Ethereal Glass (OLED black `#050505`, radial mesh
  orbs, vantablack cards with `backdrop-blur-2xl` + white/10 hairlines);
  Editorial Luxury (warm cream `#FDFBF7`, sage/espresso, variable serif headings,
  ~3% film-grain overlay); Soft Structuralism (silver-grey/white, massive bold
  grotesk, ultra-diffused ambient shadows).
- **Layout archetypes (pick 1):** Asymmetrical Bento (masonry grid of varied
  spans); Z-Axis Cascade (overlapping cards, slight `-2deg`/`3deg` rotation);
  Editorial Split (massive type left, scrollable visual right). All collapse to
  single-column `w-full px-4 py-8` below 768px, rotations and overlaps removed.
- **Signature component - the Double-Bezel:** never place a card flat on the bg.
  Outer shell (`bg-black/5` or `white/5`, `ring-1 ring-black/5`, `p-1.5`,
  `rounded-[2rem]`) wrapping an inner core with its own fill, an inner highlight
  (`shadow-[inset_0_1px_1px_rgba(255,255,255,.15)]`), and a concentric smaller
  radius (`rounded-[calc(2rem-0.375rem)]`). Pill CTAs nest a trailing-arrow icon
  in its own circular wrapper flush to the right padding.
- **Motion:** custom curves (`cubic-bezier(0.32,0.72,0,1)`), durations 700ms+.
  Fluid-island floating-pill nav, hamburger morphing to an X, staggered mask
  reveals on menu open, magnetic button physics, heavy scroll fade-up
  (`translate-y-16 blur-md opacity-0` → settled). Spring physics
  (`stiffness: 100, damping: 20`), no linear easing anywhere.
- **Spatial rhythm:** double the padding (`py-24` to `py-40`), let it breathe.

---

## Choosing between recipes

- Trust-first, document-heavy, calm B2B, content product → **minimalist**.
- Data-dense, technical, declassified-blueprint, anti-consumer statement →
  **brutalist**.
- Premium consumer, agency, portfolio, launch with budget for motion → **soft**.

When the brief is genuinely one of the named *systems* (Material, Fluent,
Carbon, GOV.UK, etc.) rather than an aesthetic, do not hand-roll any of these.
Use the official package per `design-systems.md`.
