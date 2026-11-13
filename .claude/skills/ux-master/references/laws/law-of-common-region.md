# Law of Common Region

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Law of Uniform Connectedness](law-of-uniform-connectedness.md), [Selective Attention](selective-attention.md).

## In one line

Elements inside the same clearly bounded area are seen as a group.

## What it asks of an interface

- A shared boundary tells people what belongs together and where one section ends and the next begins.
- A border around elements creates a common region.
- So does a shared background.
- A region is a strong signal. It overrides spacing: two distant items in one box read as related, and two close items in different boxes read as separate.

## When it applies

- Cards, panels, table rows, form sections, dialogs, toolbars, list items with several parts.
- Most useful when spacing alone cannot make the grouping clear, for example in dense layouts.

## Detect a violation

**In code**

- A control rendered outside the container of the content it acts on: a card's action button placed after the card's closing tag, a form's submit outside the form's panel, a table's bulk-action bar detached from the table.
- Unrelated content sharing one container: two separate tasks in one card or panel.
- Nested containers several levels deep (a card in a card in a panel), each with its own border or background, so boundaries stop meaning anything.
- Every element given its own bordered box, so no grouping is expressed at all.
- List or table rows with no row boundary (no divider, zebra background or spacing), making it unclear which values belong to which row.
- Sections of a long page with no visual boundary and no heading.

**In a screenshot or design file**

- Trace each visible boundary and list what is inside. Is everything inside related, and is anything related left outside?
- Boxes within boxes.
- Buttons floating between two cards so it is unclear which they belong to.

## Example

**Bad:** Three pricing cards, each with its "Choose plan" button placed below the card's border in a separate row, so the buttons read as a group of their own.

**Good:** Each card's button sits inside the card's border, under that plan's price, so plan and action read as one unit.

## When laws conflict

- Against Law of Prägnanz and Occam's Razor (less visual structure): use proximity and whitespace first. Add a border or background only where spacing alone is ambiguous. Too many regions is its own finding.
- Against Law of Proximity: a region beats spacing. If a boundary and the spacing disagree, people believe the boundary, so fix the boundary.
- With Law of Uniform Connectedness: both are stronger than proximity or similarity. Use the lightest one that removes the ambiguity.

## Origin

The classic Gestalt grouping principles (proximity, similarity, continuity, closure) were set out by Max Wertheimer, Kurt Koffka and Wolfgang Köhler in the early 20th century. Common region was added to the list by Stephen Palmer in 1992.

Cite as: Stephen Palmer, "Common region: A new principle of perceptual grouping", Cognitive Psychology (1992).
