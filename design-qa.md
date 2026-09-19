# Design QA — Opening Aurora Sequence + Chapter 03 Palette

## Source Visual Truth

- Current motion specification: button glow → cover copy fade → ice-blue center line → aurora curtains sweep from both sides → bilingual destination title → chapter reveal.
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

- Fonts and typography: existing serif/sans hierarchy is preserved; the Chinese destination title and its English subtitle remain readable during the dark transition.
- Spacing and layout rhythm: title card remains centered; desktop and mobile cover widths show no horizontal overflow.
- Colors and visual tokens: cover uses restrained warm paper, ice blue, lavender and coral; transition uses deep blue, cyan, violet and star white.
- Image quality and asset fidelity: the misleading `Aurora_Above_The_Glass.mp4` was removed after live capture showed embedded oversized typography and glass imagery. The final effect is abstract light only, so it does not reintroduce the rejected AI-heavy hero style.
- Copy and content: the transition no longer shows `Chapter 01`; all destinations use a Chinese title with an English subtitle.

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

## 2026-09-19 Content And Transition Refinement

- Desktop viewport: 874 × 698 CSS px. Mobile viewport: 390 × 844 CSS px.
- Listening-card title and description center points matched in all three chapters; measured desktop center delta was `0px` for Encounter, Acquaintance, and Accompany.
- Visible track number and filename metadata were removed from all three cards. Play controls, progress semantics, status labels, and single-track behavior remain wired.
- Transition results: `相遇 Encounter`, `相識 Acquaintance`, `相處 Accompany`, and `終章 Finale`. `.transition-kicker` count was `0`, so the opening transition no longer displays `Chapter 01`.
- Desktop and 390px mobile horizontal overflow: `0px`.
- Browser console after the final reload and mobile interaction flow: `0 errors / 0 warnings`.
- Rendered evidence: `output/playwright/listening-card-desktop.png`, `output/playwright/listening-card-mobile.png`, and `output/playwright/transition-mobile.png`.
- Audio playback was not tested and no audio file was read, played, analyzed, or uploaded.

content refinement result: passed

## 2026-09-19 Player Timeline Refinement

- Player controls now use the full card width in the order play button → progress bar → current `mm:ss` position.
- At 874 × 698, the control width was `732.19px` and the progress bar width was `609px`; at 390 × 844, the progress bar width was `176.81px`.
- A browser-only mock set the current position to 65 seconds of a 180-second duration. The UI rendered `01:05`, `aria-valuenow="36"`, and a `36.1111%` fill without loading or playing an audio file.
- Desktop and mobile horizontal overflow: `0px`. Browser console: `0 errors / 0 warnings`.
- The complete request list contained only `index.html` and the three Encounter images; no MP3 or WAV request occurred.
- Rendered evidence: `output/playwright/player-timeline-desktop.png` and `output/playwright/player-timeline-mobile.png`.
- Finale copy was verified as: `願這三段旋律，在妳需要的時候，化作一點微光；也願往後的日子，仍有新的樂章持續譜寫每一個值得期待、值得記錄的日常。`

player timeline refinement result: passed

## 2026-09-19 Local Audio Path Repair

- Root cause: all six HTML audio source paths differed from the local filenames.
- Updated each player to use its existing WAV filename. The previous MP3 fallback files were removed by the owner and are no longer referenced.
- Path-only verification: all three WAV source paths returned `Exists = True`.
- Privacy boundary preserved: no audio file was opened, played, decoded, analyzed, uploaded, or committed during verification.
- Publication approval: on 2026-09-19, the project owner explicitly authorized publishing the three named WAV files to the configured GitHub Pages repository.
- Browser codec/playback verification remains user-owned because it would require the browser to read and decode the audio file.

local audio path result: ready for user playback check
