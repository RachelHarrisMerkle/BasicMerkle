# Law of Prägnanz

UX Theory card. Also called: Law of Simplicity, Law of Good Figure. Audit lens: Visual structure.

Related cards in the deck: [Tesler's Law](teslers-law.md), [Selective Attention](selective-attention.md).

## In one line

People read a complex or ambiguous image as the simplest form they can, because that takes the least mental effort.

## What it asks of an interface

- The eye looks for simple, ordered shapes and reduces complicated ones to them.
- Simple figures are easier to take in and to remember than complex ones.
- Several parts will be seen as one unified shape if they can be. A layout built on a clear underlying shape (a grid, columns, a list) is read faster than one that is not.

## When it applies

- Page structure and alignment, icons and logos, charts and diagrams, cards and tiles.
- Any place where the overall shape of the layout should tell people how to read it.

## Detect a violation

**In code**

- No consistent grid or alignment: siblings with different widths, offsets or start edges for no content reason. Look for many one-off widths and margins.
- More alignment axes than needed: left-aligned, centered and right-aligned blocks mixed in one section.
- Cards or tiles in one row with different heights, paddings or internal structure.
- Decorative shapes, dividers, borders and backgrounds that do not mark a real boundary.
- Icons drawn with heavy detail at small sizes, or mixed icon styles (outline and filled, different stroke weights) in one set.
- Charts with unnecessary effects, dense gridlines or many near-identical series colors.

**In a screenshot or design file**

- Reduce the screen to boxes in your head. Is there a simple arrangement (columns, rows, a grid), or do the boxes scatter?
- Count the vertical lines that left edges fall on. Fewer is simpler.
- Icons that need study to recognize.

## Example

**Bad:** A dashboard whose tiles have six different widths, sit on no common edges, and mix outlined and filled icons.

**Good:** Tiles on a 12-column grid, each row aligned on shared edges, one icon style at one stroke weight.

## When laws conflict

- Against Law of Common Region (add boundaries): add a boundary only if grouping is unclear without it.
- Against Signifiers and Discoverability: simplicity never justifies removing a label or a cue people need.
- Against Tesler's Law: a simple look must not be bought by pushing complexity onto the person using it. Simple to read and simple to use are different things; check both.

## Origin

Prägnanz, often translated as "good figure" or "simplicity", is the central principle of Gestalt psychology as developed by Max Wertheimer, Kurt Koffka and Wolfgang Köhler in the early 20th century: perception tends toward the simplest, most stable organization available.

Cite as: Max Wertheimer, Kurt Koffka and Wolfgang Köhler, Gestalt psychology (early 20th century).
