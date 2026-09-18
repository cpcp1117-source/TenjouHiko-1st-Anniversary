# Design QA — Visual MVP Cover

## Evidence

- Source visual truth: `docs/reference/selected-cover-option-3.png`
- Implementation screenshot: `qa-output/cover-implementation.png`
- Source pixels: 1440 × 1024
- Implementation pixels: 1440 × 1024
- CSS viewport: 1440 × 1024
- Device scale factor: 1
- State: Prelude / cover before opening the letter
- Browser renderer: Chrome for Testing 154 headless

## Full-view Comparison Evidence

The source and implementation were each opened at the same pixel size. The implementation visibly preserves the selected direction's open ivory textile storybook, aurora window, ice-blue ribbon, pale-gold embroidery, centered title hierarchy, sound note and primary action. Live HTML replaces the mockup's baked-in text and button.

A combined side-by-side browser capture could not be completed because repeated Chrome headless comparison launches remained open without writing the requested comparison screenshot. The helper processes were stopped without touching the user's regular Chrome sessions.

## Focused Region Evidence

Not completed. The cover title, body copy and primary action are readable in the full-size implementation capture, but the required combined focused comparison artifact is unavailable.

## Findings

- [P1] Required combined comparison evidence is unavailable
  - Location: cover, complete viewport.
  - Evidence: both source and implementation captures exist at 1440 × 1024, but the tool did not produce one combined comparison image.
  - Impact: Product Design QA cannot formally claim visual fidelity from separate views.
  - Fix: reopen both images in one browser/canvas surface or use the in-app browser review surface to compare them together.

- [P1] Primary transition has not been browser-interaction tested
  - Location: `開啟這封信` → Chapter 01.
  - Evidence: JavaScript syntax is valid, but the Playwright CLI did not return an operable session.
  - Impact: the visual MVP's main interaction may still have timing, focus or state defects.
  - Fix: test click, transition veil, Chapter 01 reveal, back navigation and console in the in-app browser.

- [P2] Mobile implementation lacks rendered evidence
  - Location: 390 × 844 cover and Chapter 01.
  - Evidence: responsive rules exist, but no mobile browser screenshot was captured.
  - Impact: background cropping, text density or controls may not fit as intended.
  - Fix: capture cover and first chapter at 390 × 844 and correct any overflow or low-contrast areas.

## Required Fidelity Surfaces

- Fonts and typography: live Traditional Chinese title and body copy are readable and follow the source hierarchy; exact font fidelity remains unverified.
- Spacing and layout rhythm: desktop cover composition follows the selected source and fits at 1440 × 1024; mobile remains unverified.
- Colors and visual tokens: ivory, midnight blue, ice blue, lavender aurora and pale gold visibly match the selected direction.
- Image quality and asset fidelity: generated cover background is sharp at 1440 × 1024 and is used as a real raster asset rather than recreated with placeholder CSS art.
- Copy and content: required anniversary eyebrow, title, description, sound note and primary action are present as live HTML.

## Comparison History

### Iteration 1

- Earlier issue: MVP used a generic dark card and did not visibly express the requested art direction.
- Fix made: generated and integrated a blank illuminated storybook cover plus a matching first-chapter textile page; rewrote cover and chapter styling around those assets.
- Post-fix evidence: `qa-output/cover-implementation.png`.
- Result: visual direction materially improved; formal comparison and interaction gates remain blocked.

## Implementation Checklist

1. Refresh and inspect the cover in the in-app browser.
2. Test the open-letter transition and Chapter 01 reveal.
3. Inspect 390 × 844 mobile layout.
4. Record console errors.
5. Repeat same-surface source/implementation comparison.

## Follow-up Polish

- Tune title size and vertical position after live browser feedback.
- Adjust transition duration if the page-turn reveal feels too slow.
- Decide whether the progress capsule should remain visible in Chapter 01.

final result: blocked
