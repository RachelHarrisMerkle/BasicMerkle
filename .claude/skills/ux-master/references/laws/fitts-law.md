# Fitts' Law

UX Theory card. Also called: Fitts's Law. Audit lens: Targets and movement.

Related cards in the deck: [Hick's Law](hicks-law.md), [Cognitive Load](cognitive-load.md).

## In one line

The time to hit a target depends on how far away it is and how big it is. Small, distant targets are slow and error-prone.

## What it asks of an interface

- Make targets big enough to hit accurately the first time.
- Leave space between targets so a near miss does not hit the wrong one.
- Put targets where they are easy to reach: close to where attention and the pointer or thumb already are.
- The relationship is logarithmic. Making a tiny target bigger helps a lot; making a big one bigger helps little.
- The clickable area is what counts, not the visible shape. Padding and hit regions are part of the target.

## When it applies

- Every clickable or tappable control, most of all on touch screens, and for primary actions, close buttons, form controls and row actions.
- Placement of a task's next action relative to where the task just ended.
- Screen edges and corners with a mouse are easy targets because the pointer stops there. This does not apply to touch.

## Detect a violation

**In code**

- Interactive elements whose hit area is below a published minimum. The floors, strictest last:
  - WCAG 2.2 success criterion 2.5.8 (level AA): at least 24 by 24 CSS pixels. The exceptions include a smaller target with enough space around it (a 24 pixel circle centered on it does not touch another target), a link inside a sentence, and an unmodified browser control.
  - Apple Human Interface Guidelines: a button needs a hit region of at least 44 by 44 points (60 by 60 on visionOS). Apple lists 28 by 28 points as the minimum control size on iOS and iPadOS, and 28 by 28 default with 20 by 20 minimum on macOS.
  - WCAG 2.2 success criterion 2.5.5 (level AAA): at least 44 by 44 CSS pixels.
  - Google's Android accessibility guidance: at least 48 by 48 dp, with 8 dp or more between targets.
- Work out the real size: width, height, `min-width`, `min-height`, padding, line height and icon size together. An icon of 16 to 24 pixels with no padding is the usual failure. Check close buttons, icon buttons, checkboxes, radio buttons, pagination, chips and links in dense lists.
- Adjacent targets with no gap (`gap: 0`, touching borders), especially a destructive action touching a safe one.
- Text links as the only way to trigger a primary action.
- Form labels not connected to their control (`<label for>` or wrapping label missing), so clicking the label does nothing and the target is only the small box.
- The primary action placed far from the last input: at the top of a long form, or in the opposite corner.

**In a screenshot or design file**

- Measure the smallest interactive elements against the minimum for the platform: a 44 by 44 point hit region for buttons on Apple platforms (Human Interface Guidelines), 48 by 48 dp with 8 dp between targets on Android (Google's accessibility guidance), and on the web 24 by 24 CSS pixels for WCAG 2.2 level AA (2.5.8) or 44 by 44 for level AAA (2.5.5). From a screenshot, estimate from known sizes and mark the figure as an estimate.
- Tightly packed icon rows.
- A primary button that is smaller than secondary elements around it.
- On mobile layouts, primary actions at the very top of a tall screen, the hardest place for a thumb to reach.

## Example

**Bad:** A 16 pixel "x" icon with no padding as the only way to close a dialog, placed 4 pixels from a "Delete" icon of the same size.

**Good:** A close button with a 44 by 44 hit area, separated from other actions, and a full-width primary button directly under the last field of the form.

## When laws conflict

- Against information density in expert tools: on touch, target size wins. On pointer-driven desktop tools, compact controls are acceptable down to the WCAG AA floor if spacing is adequate. Say which platform you assumed.
- Against Constraints and error prevention for destructive actions: do not make a dangerous target tiny to protect it. Keep it a normal size, separate it from the primary action and style it differently.
- Against Mapping: keep a control next to what it affects even if that is not the fastest spot to reach, and add a second copy where reach matters.

## Origin

Psychologist Paul Fitts showed in 1954 that the time to move to a target increases with the distance to it and decreases with its width, and that fast movements to small targets produce more errors. The law has been applied to pointing devices since the early days of human-computer interaction research.

Cite as: Paul Fitts, "The information capacity of the human motor system in controlling the amplitude of movement", Journal of Experimental Psychology (1954).
