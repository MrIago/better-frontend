# Token system: from a design plan to CSS that won't fight itself

The SKILL.md asks for "a compact token system with color, type, layout, and
signature." This is how to structure it so the build stays consistent and the
selectors don't cancel out. Three layers, each referencing the one below.

```
Primitive  →  raw values        --blue-600: #2563EB;  --space-4: 1rem;
Semantic   →  purpose aliases    --color-accent: var(--blue-600);
Component   →  usage             --button-bg: var(--color-accent);
```

Hardcode nothing past the primitive layer. Change a brand color in one place,
not forty.

## Primitive scales (starting points — bend them to the brief)

- **Spacing** on a 4px base: 2, 4, 8, 12, 16, 24, 32, 48, 64, 96. Pick from the
  scale; don't invent `13px` paddings.
- **Type scale** by ratio. Major third (×1.25) for calm contrast, perfect fourth
  (×1.333) for drama. e.g. 1.25×: 13 / 16 / 20 / 25 / 31 / 39 / 49 / 61.
- **Radius:** 0, 2, 4, 8, 12, 16, full. One choice, applied with intent.
- **Shadow:** a layered ramp (sm → 2xl), tinted from the palette, not flat black.
- **Duration:** 100 / 150 / 200 / 300 / 500ms (see `motion.md`).
- **Z-index** as named tiers: dropdown 1000, sticky 1100, modal 1200, popover
  1300, tooltip 1400 — never ad-hoc `z-index: 9999`.

## Semantic layer (the names you actually use)

`--color-bg`, `--color-fg`, `--color-muted`, `--color-accent`,
`--color-accent-hover`, `--color-border`, `--color-ring`,
`--space-section`, `--space-component`, `--font-display`, `--font-body`,
`--duration-fast`. Naming convention: `--{category}-{role}-{state}`
(`--color-accent-hover`).

## Dark mode

Override the **semantic** layer only, never primitives or components:

```css
:root      { --color-bg: #fff;     --color-fg: #111; }
.dark      { --color-bg: #0d0f12;  --color-fg: #e9e9e9; }
```

## Selector hygiene (the bug the SKILL.md warns about)

Type-based (`.section`) and element-based (`.cta`) selectors at equal specificity
silently override each other on shared properties — usually section
padding/margin. Keep spacing on a single owner (e.g. only `.section` sets
vertical rhythm; `.cta` never touches it), or scope explicitly
(`.section > .cta`). When two rules touch the same box, decide which one wins on
purpose.
