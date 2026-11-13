# Law of Closure

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Selective Attention](selective-attention.md).

## In one line

People fill in missing parts of a shape to see a complete whole.

## What it asks of an interface

- Closure lets icons be simple. A few strokes are enough because people complete the picture. But test that people read the icon as intended, and add a text label when they might not.
- A deliberately cut-off item signals that there is more. A carousel that shows part of the next card invites people to scroll.
- The risk is the reverse: a layout that looks complete when it is not. If content ends cleanly at the edge, people assume there is nothing further.
- Give enough of the shape. With too little, people cannot fill in the rest.

## When it applies

- Icons and logos, loading placeholders, carousels and horizontal scrollers, truncated text and lists, the fold on a long page, progress rings.

## Detect a violation

**In code**

- Horizontal scrollers and carousels where the visible items fit the container exactly, so nothing is cut off and nothing shows that more exists. No partial item, arrow, dots or count.
- A page section that ends at the bottom of the first screen with a full-width band or large spacing, so the page looks finished. This is the illusion of completeness.
- Truncated text or lists with no ellipsis, "Show more" or count ("+3 more"), or truncation with no way to see the full content.
- Icon-only controls built from abstract or heavily simplified shapes with no label (see Signifiers).
- Skeleton placeholders whose shapes do not resemble the content that will load, so the page jumps when it arrives.
- Progress rings or bars that look complete before the task is done.

**In a screenshot or design file**

- At the bottom and right edges of each scrollable area: is anything cut off to show continuation?
- Icons that need a second look.
- A first screen that looks like a finished page.

## Example

**Bad:** A row of exactly four product cards filling the width with no arrows, where eight more are reachable only by swiping.

**Good:** The row shows four and a half cards, with the fifth visibly cut off, plus arrows and "1 of 3" paging.

## When laws conflict

- Against Law of Prägnanz and aesthetic tidiness: a tidy edge that hides content loses. Let content break the edge when there is more.
- Against Signifiers: closure can hint; it cannot explain. Important or irreversible actions get a text label, however clear the icon seems to its designer.
- Against Cognitive Bias: do not use an apparently complete screen to hide terms, costs or options further down.

## Origin

One of the Gestalt principles of perception developed by Max Wertheimer, Kurt Koffka and Wolfgang Köhler in the early 20th century: people tend to perceive incomplete figures as complete.

Cite as: Max Wertheimer, Kurt Koffka and Wolfgang Köhler, Gestalt psychology (early 20th century).
