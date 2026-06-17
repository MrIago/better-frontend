# Anti-slop: the tells, and restraint you can measure

The SKILL.md names the three AI-default *looks*. This goes one level lower: the
component-level reflexes that read as generated regardless of look, and how to
make "spend your boldness in one place" verifiable instead of aspirational.

## The reflexes to catch (don't ship these by default)

- **Inter / Roboto / Poppins / Space Grotesk by reflex.** Fine when the brief
  asks for them; never as the unexamined default. Pick a face for a reason.
- **Purple/blue gradient** on the primary background, or gradient text on a
  headline. The single most recognizable "AI made this" signal.
- **Everything centered.** A hero centered in a full-viewport column, then the
  next section centered, then the next. Asymmetry and a real grid read as
  designed.
- **Uniform border-radius** (12–16px) on every card, button, input, and image.
  Vary it or commit to one radius *intentionally* (incl. 0).
- **The SaaS-blue CTA** (`#3B82F6`) on white. A default, not a choice.
- **Glassmorphism + soft drop-shadow on everything** to fake depth. Depth comes
  from spacing and hierarchy first.
- **Card grid of identical cards nested in more cards.** Structure should come
  from spacing and rhythm, not from boxing every element.
- **Emoji as section icons**, "Welcome to our platform" copy, three feature
  cards with a generic line-icon each.

## Restraint you can measure

"Keep everything around the signature quiet" is checkable:

- **Color budget.** Primary/neutral ≈ 60–70% of the canvas, one accent ≤ ~15%,
  a rare tertiary ≤ ~5%. **Remove test:** desaturate the accent to gray — the
  design should still read as intentional. If it collapses, the color was
  carrying weight the structure should carry.
- **Type budget.** One display face (≤ 3 sizes), one body face, ≤ 3 weights in
  use, ≤ 2 line-lengths. More than that is usually indecision, not range.
- **Chanel test.** Before shipping, remove one element. If nothing breaks, it was
  decoration.
- **Convergence check.** Re-run the brief in your head as a generic prompt. If
  you'd arrive at the same palette/face/layout for *any* similar brief, you
  picked a default — change the part that converged and say why.

## Vanity to avoid in the build itself

Over-engineering reads as slop too: a "design system" defined but used once,
custom-built components for solved problems (use shadcn/Radix/established
primitives), one component abstracted on its first and only use, config longer
than the code it configures. Build the concrete thing; abstract on the second
real use.
