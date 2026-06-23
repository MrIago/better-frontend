# Image references: art-directing design comps, and image-first build

Two related jobs live here. (1) When an image-generation tool is available,
generating premium *reference comps* (web sections, mobile screens, brand
boards) you or a coding agent will build from. (2) The image-first workflow:
generate references, analyse them deeply, then implement to match. Pull this in
when the deliverable is reference imagery, or when a visual build benefits from
designing in images before code.

The art-direction rules below sit on top of everything in `anti-slop.md`,
`design-vocabulary.md`, and `typography.md` - those still apply to what the
images depict.

---

## The image-first workflow (generate → analyse → code)

For a visually-led build, do not start by free-coding. The order is mandatory
when image generation is available:

1. **Infer the section/screen count** (defaults below).
2. **Generate the reference image(s) first** - one focused image per section or
   screen, not one compressed board.
3. **Generate extra detail/extraction images** where text, buttons, or spacing
   are too small to read. Regenerate a section fresh rather than cropping an old
   image (cropping destroys spacing, type scale, and proportion).
4. **Analyse each image as a spec**, not a vibe: extract exact readable text
   (headline, subhead, CTA labels), type scale and weight relationships, spacing
   and gutters, radius logic, button hierarchy, palette, image treatment, grid.
5. **Implement to match closely.** Preserve layout, spacing rhythm, section
   order, type mood, component family. Do not drift into a generic coded
   reinterpretation (the common failure: strong references, generic build).
6. **Resolve ambiguity** by preserving the design language first, generating an
   extra detail image second, only then choosing a faithful default.

## Output rule: one image per section, always

A landing page with 8 sections produces 8 images. Never compress multiple
sections into one frame, never return one tall full-page slice, never return one
"best" image and skip the rest. If only one image can render per call, produce
them sequentially in the same response, labelled "Section X of N: <name>".

Default counts when unstated: hero → 1; landing page / product page / portfolio
→ 6; full website / marketing site → 8. Web comps are horizontal (16:9, 16:10,
21:9). Mobile screens sit in a clean phone mockup.

## The combinatorial variation engine (web comps)

To avoid repetitive output, pick one option per axis and commit. Do not mash
everything together.

- **Theme:** Pristine Light · Deep Dark · Bold Studio Solid · Quiet Premium
  Neutral.
- **Background character:** technical grid/dotted · solid + ambient gradient
  depth · full-bleed cinematic image · textured/material surface.
- **Hero architecture:** cinematic centred minimalist · asymmetric split ·
  floating polaroid scatter · inline-typography behemoth · editorial offset ·
  massive image-first with restrained text.
- **Section system:** modular bento · alternating editorial blocks · poster-stack
  storytelling · gallery cadence · Swiss grid · asymmetric marketing flow.
- **Signature components (pick exactly 4):** diagonal staggered masonry · 3D
  cascading card deck · hover-accordion slices · gapless bento · brand marquee ·
  turning polaroid arc · vertical rhythm lines · off-grid editorial · product UI
  panel stack · split testimonial wall · oversized metrics strip · layered image
  crop frames.
- **Motion-implied (pick 2):** scrubbing text reveal · pinned narrative · stagger
  float-up · parallax drift · accordion expansion · cinematic fade-through.
- **Per-section composition anchor:** vary across the page (centred statement,
  top-left lead, bottom-left over image, bottom-right CTA cluster, classic
  left-third caption used sparingly, inverted right-third, centred-low,
  off-grid, stacked-centre, image-as-canvas). At least 3 anchors appear; the
  left-text/right-image classic is the most overused default - do not open on it
  by reflex.
- **Per-section background mode:** vary across the page (solid + inline asset,
  texture, full-bleed image + tonal overlay, editorial side-image, image-as-
  canvas, flat block + crop, palette-matched tonal gradient, duotone, radial
  vignette + product, micro-noise gradient, color-blocked diptych).
- **Hero scale (per page):** Giant Statement · Mid Editorial · Mini Minimalist.
  Mini is confident restraint, not weakness.
- **Narrative spine (pick 1, thread it):** artifact · journey · precision
  instrument · living system · stage/spotlight · archive/dossier.
- **Second-read moment (pick exactly 1):** one quiet motif placed once that aids
  scan order or recall (asymmetric bleed, one oversized numeral, a material
  switch, a side-rail note, a brand-colour macro crop).

## Mobile screens

- **Decide platform first:** iOS-native premium · Android-native premium ·
  cross-platform neutral. Do not mix iOS and Android patterns carelessly.
- **Lock a design bible** across the whole set: platform mode, device frame and
  scale, palette, type scale, radius, icon style, texture intensity, navigation
  model. Screen 4 must not drift into a different app.
- **Generate a believable flow**, not random screens (onboarding → auth → home;
  browse → detail → cart → confirmation). Each screen earns its place in the
  journey.
- **Respect safe areas** (status bar, notch, tab bar, home indicator). A mobile
  screen is an app, not a poster, and not a website squeezed into a phone.
- **Phone mockup by default**, clean and evenly margined, content-first (the
  frame supports the screen, never dominates). Text comfortably readable, never
  tiny. First screen especially calm: 1-3 short lines, one clear action.
- **Texture and image-behind-text** are encouraged (grain, paper, fades, masks)
  when they serve the category, with readability protected by scrims/fades.

## Brand boards

- **Strategy before pixels:** category, audience, emotional promise, core
  metaphor, what to avoid. The logo comes from research and reduction, not random
  symbols. Logo methods: monogram + meaning, product-action symbol, metaphor
  fusion, negative space, construction geometry (combine two at most).
- **Default board:** 3x3 grid on a dark or light presentation canvas with strong
  gutters and restrained density. Panels: logo cover · logo construction ·
  digital application · brand essence/tagline · color system · typography ·
  physical application · image direction · system detail.
- **One dominant palette**, accent repeating across panels. Very little text
  (brand name, one tagline, a few labels, short UI chips). Mockups are identity
  applications (browser chrome, app icon, terminal, card, seal), not feature
  demos with fake dense data.

## Anti-slop for generated imagery (in addition to anti-slop.md)

Avoid: one giant unreadable collage; endless centred sections; identical card
rows; cloned left-text/right-image; cards-inside-cards-inside-cards; giant
rounded wrapper sections; default purple/blue AI gradients; floating blobs;
unmotivated glassmorphism; over-rendered noise that hides layout; giant heading
+ weak tiny subcopy; lazy all-caps; fake brand names (Acme, Nexus, NovaCore);
filler copy (unleash, elevate, next-gen, seamless); fake KPI/stat columns and
fake chart dashboards unless the brief needs them; pseudo-system pills and
decorative status labels. Keep the page breathing: even section spacing,
generous negative space, one disciplined second-read moment.
