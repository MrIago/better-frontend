# Motion: values, not vibes

The SKILL.md says motion should serve the subject and that scattered effects read
as generated. When motion *is* called for, these are the concrete values that
make it feel physical instead of random.

## Easing — pick by what's happening

```
entering   ease-out      cubic-bezier(0, 0, 0.2, 1)      decelerate in
exiting    ease-in       cubic-bezier(0.4, 0, 1, 1)      accelerate out
moving     ease-in-out   cubic-bezier(0.4, 0, 0.2, 1)    state change
playful    spring/back   cubic-bezier(0.34, 1.56, 0.64, 1)   1 overshoot, settles
loops      linear        spinners / marquees only
```

Default to ease-out for almost everything; reserve spring for one playful moment.
Nothing should bounce repeatedly or spring past its mark and stay there.

## Duration — by weight, not taste

- Lightweight (icon, badge, hover): ~150ms
- Standard (card, panel, dropdown): ~300ms
- Weighty (modal, page transition): ~400–500ms

Quick reference: button press 100ms, hover 150ms, tooltip 200ms, tab 250ms,
modal 300ms, page 400ms.

## Patterns

- **Orchestrate, don't scatter.** One page-load sequence (hero → text +0.2s →
  CTA +0.4s) lands harder than ten independent effects. Stagger children
  ~0.08–0.1s; perfectly uniform staggers feel robotic, so vary slightly.
- **Reveal on scroll** at ~20% from the bottom of the viewport, once.
- **Animate only `transform` and `opacity`** — they're GPU-composited.
  Animating width/height/margin/top thrashes layout and stutters.

## Slop tells to avoid

Global rotate/skew on hover, scale > 1.05 on hover (reads cheap), fade to/from
opacity 0 with no movement (looks dead), everything springing.

## Non-negotiable

Honor reduced motion — collapse to instant or fade-only:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; }
}
```
