# Responsive & accessibility: the quality floor, made concrete

The SKILL.md commits to "responsive down to mobile, visible keyboard focus,
reduced motion respected." These are the specifics that satisfy it.

## Responsive

- **Breakpoints:** XS 0–479 (small phone) · SM 480–767 (phone) · MD 768–1023
  (tablet) · LG 1024–1439 (laptop) · XL 1440+ (desktop). Let content, not
  devices, decide where a layout actually breaks.
- **Design mobile-first**, then add breakpoints as the content needs room.
- **Test at:** 375, 390, 768, 1024, 1280+. Nothing overflows, overlaps, or
  reflows into nonsense; long words/code blocks scroll rather than break layout.
- **Fluid type** with `clamp()` so headings scale between breakpoints (see
  `typography.md`).

## Accessibility (WCAG AA as the floor)

- **Contrast:** ≥ 4.5:1 for body text, ≥ 3:1 for large text and meaningful
  graphics/icons. The accent must clear this against its background — pretty but
  illegible is a fail.
- **Touch targets** ≥ 44×44px; add `touch-action: manipulation` to drop the
  300ms tap delay.
- **Keyboard:** every interactive element reachable by Tab in logical order,
  with a *visible* focus ring (don't `outline: none` without a replacement). Use
  `:focus-visible` for a ring only on keyboard focus.
- **Semantics:** real `<button>`/`<a>`/`<nav>`/`<main>`/headings before ARIA;
  add `aria-label`/`role` only where semantics fall short. Every input has a
  label.
- **Motion:** honor `prefers-reduced-motion` (see `motion.md`).
- **States:** design the empty, loading, and error states too — an empty screen
  is an invitation to act, an error says what went wrong and how to fix it.

## A 60-second self-audit before shipping

Hierarchy reads at a glance · spacing rhythm is consistent (no 1–2px drift) ·
alignment holds to the grid · type scale is honored · color budget respected
(see `anti-slop.md`) · focus states visible · contrast passes · 320px mobile
looks intentional, not squeezed. Screenshot it — a picture catches what reading
the code won't.
