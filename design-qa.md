# Design QA — Opening Aurora Sequence + Chapter 03 Palette

## Source Visual Truth

- User motion specification: button glow → cover copy fade → ice-blue center line → aurora curtains sweep from both sides → `Chapter 01` / `相遇 Encounter` → Chapter 01 reveal.
- Intended duration: approximately 1.5–2 seconds.

## Rendered Evidence

- Desktop cover: `qa-output/opening-final-cover-desktop.png`
- Mobile cover: `qa-output/opening-final-cover-mobile.png`
- Copy fade / veil entry: `qa-output/opening-curtain-0350.png`
- Left and right curtain sweep: `qa-output/opening-curtain-0700.png`
- Chapter title: `qa-output/opening-curtain-1100.png`
- Chapter 01 revealed: `qa-output/opening-curtain-1900.png`
- Desktop viewport: 1440 × 1024 CSS px, deviceScaleFactor 1.
- Mobile viewport: 390 × 844 CSS px, deviceScaleFactor 1.

## Full-view Comparison Evidence

The browser-rendered sequence follows the six requested beats. The desktop cover keeps the editorial typography while adding a low-contrast ice-blue, lavender and coral aurora field. The transition changes from the light cover into a deep-blue veil, draws the center light, brings cyan and violet curtains inward from opposite sides, then presents the chapter label before revealing the encounter section.

## Focused Region Evidence

Focused evidence was captured at 0.35s, 0.70s and 1.10s because the direction and timing of the curtain, light line and title cannot be judged from the final screen alone.

## Required Fidelity Surfaces

- Fonts and typography: existing serif/sans hierarchy is preserved; `Chapter 01`, `相遇` and `Encounter` remain readable during the dark transition.
- Spacing and layout rhythm: title card remains centered; desktop and mobile cover widths show no horizontal overflow.
- Colors and visual tokens: cover uses restrained warm paper, ice blue, lavender and coral; transition uses deep blue, cyan, violet and star white.
- Image quality and asset fidelity: the misleading `Aurora_Above_The_Glass.mp4` was removed after live capture showed embedded oversized typography and glass imagery. The final effect is abstract light only, so it does not reintroduce the rejected AI-heavy hero style.
- Copy and content: the requested `Chapter 01` and `相遇 Encounter` labels are present; original anniversary copy is unchanged.

## Interaction And Accessibility

- Primary click-through tested from Prelude to Encounter.
- Final state at approximately 1.9 seconds: `encounter` visible, transition classes removed, document title updated.
- Browser JavaScript exceptions: 0.
- Browser resource errors: 3 expected missing encounter story images; existing text fallback handled them without breaking the page.
- `prefers-reduced-motion: reduce` keeps an immediate, non-animated scene change and hides decorative motion layers.

## Comparison History

### Iteration 1

- Finding: the existing MP4 displayed large English typography and glass objects instead of a restrained aurora.
- Fix: removed the video from both cover and transition; retained only abstract light and color.
- Post-fix evidence: `opening-final-cover-desktop.png`, `opening-final-cover-mobile.png`.

### Iteration 2

- Finding: the first mask formed a narrow center strip, visually reading as center-out rather than side-in.
- Fix: split the aurora into independent left and right curtains moving from outside the viewport toward the center.
- Post-fix evidence: `opening-curtain-0700.png`, `opening-curtain-1100.png`.

## Remaining P3 Polish

- The center seam between cyan and violet is intentionally visible as a meeting point; it can be softened in a later taste pass if desired.

## Chapter 03 Palette Update

- Source decision: replace the abrupt deep-night palette with the approved Moon Mist blue-grey direction.
- Before evidence: `qa-output/audit-accompany-desktop.png`.
- Desktop implementation: `qa-output/accompany-moon-mist-final-desktop.png`, 1440 × 1024 CSS px, deviceScaleFactor 1.
- Mobile implementation: `qa-output/accompany-moon-mist-final-mobile.png`, 390 × 844 CSS px, deviceScaleFactor 1.
- Finale handoff evidence: `qa-output/accompany-to-finale-desktop.png`.
- Applied tokens: background `#E6EBF2`, text `#293F58`, card `#F7F5F1`, button `#34506B`, accessible dark moon-gold `#7F612D`.
- Contrast: body text 9.01:1; card text 9.91:1; button text 8.25:1; chapter-number gold 4.80:1.
- Browser result: no horizontal overflow at 390 px and no JavaScript exceptions.
- Comparison result: Chapter 02 → Chapter 03 → Finale now stays in a continuous light tonal range; no actionable P0/P1/P2 findings remain.

final result: passed
