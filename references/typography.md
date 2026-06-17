# Typography: the craft details that separate set type from default type

The SKILL.md says type carries the page's personality. These are the concrete
settings that make it read as *set* rather than dropped in.

## Scale, measure, rhythm

- **Scale by ratio**, not by eyeballing: ×1.25 (calm) or ×1.333 (dramatic). Keep
  the steps consistent across the page.
- **Measure (line length):** 45–90 characters, ~65 ideal. Use `max-width: 65ch`,
  not a pixel guess. Too-wide body text is a slop tell.
- **Line-height:** body 1.4–1.6; display tighter, 0.9–1.1 (tightness adds drama).
- **Fluid sizing** for display: `clamp(2rem, 5vw, 4rem)` so the hero scales
  without breakpoints.

## OpenType settings that should be on

```css
body { font-feature-settings: "kern" 1, "liga" 1;
       text-rendering: optimizeLegibility; }
```

- **Kerning + ligatures** on for body and display.
- **Real small caps** via `font-variant-caps: small-caps` (needs a font with the
  `smcp` feature) — never fake them by scaling capitals.
- **Tracking on ALL CAPS:** add `letter-spacing: 0.05em`–`0.12em`. Caps set at
  0 tracking read as cramped.
- **Tabular numbers** for data/tables: `font-variant-numeric: tabular-nums`.

## Correct characters (a quiet but real tell)

Use the real glyphs, not ASCII stand-ins: `"" ''` (curly quotes), `–` en dash
for ranges, `—` em dash for breaks, `…` ellipsis (not `...`), `×` not `x`, `→`
not `->`. In JSX text, a literal `'` typed as `’` renders the escape
literally — use the real UTF-8 character in the source, or `{'’'}`, or an
HTML entity (`&rsquo; &ldquo; &mdash; &hellip;`).

## Pairing and emphasis

- Pair a characterful **display** face (used with restraint) with a neutral
  **body** face; add a **utility/mono** face only if data or captions need it.
- Don't reach for the same families you'd use on any project (see
  `anti-slop.md`).
- **Emphasis: bold *or* italic, not both.** In serifs, italic is the gentle
  emphasis; in sans, prefer bold (sans italics barely register).
