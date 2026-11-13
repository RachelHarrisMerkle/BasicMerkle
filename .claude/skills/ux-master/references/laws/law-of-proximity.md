# Law of Proximity

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Law of Similarity](law-of-similarity.md), [Selective Attention](selective-attention.md).

## In one line

Things that are close together are seen as belonging together.

## What it asks of an interface

- Nearness creates a relationship before anything is read.
- People assume close elements share a function or a meaning.
- Spacing is therefore the cheapest way to organize a screen: it lets people take in structure quickly.
- The signal comes from the difference in spacing. Space within a group must be clearly smaller than space between groups.

## When it applies

- Labels and their fields, headings and their sections, buttons and what they act on, captions and images, items in a list, error messages and their inputs.
- Every layout. This is the most often broken grouping law in generated interfaces because uniform spacing is the default.

## Detect a violation

**In code**

- Uniform spacing everywhere: one `gap`, margin or padding value used both inside groups and between them. Compare the space between a label and its field with the space between that field and the next label; the first must be clearly smaller.
- A label, helper text or error message closer to the neighboring field than to its own.
- A heading with equal space above and below, so it does not attach to the section it introduces. It should sit closer to what follows.
- Related actions separated (Save in the header, Cancel in the footer) or unrelated actions adjacent (Delete touching Save).
- A control far from the content it affects.
- Icon and label of one item spaced as widely as two separate items.

**In a screenshot or design file**

- Blur your eyes or view at thumbnail size and count the clumps. The clumps should match the logical groups.
- Ambiguous labels: one that sits midway between two fields.
- Evenly spaced lists of mixed content where groups should exist.

## Example

**Bad:** A form where every element has 16 pixels of space above and below, so each label floats equally between two fields.

**Good:** 4 pixels between a label and its field, 8 pixels to its helper text, 24 pixels before the next label and 40 pixels before the next section heading.

## When laws conflict

- Against Law of Common Region and Law of Uniform Connectedness: borders and connecting lines override spacing. If they contradict the spacing, people follow them. Prefer fixing spacing over adding boxes.
- Against density (fitting more on screen): tighten within groups before you tighten between groups. Lose the between-group gap and the structure goes with it.
- With Chunking: proximity is how chunks are made visible.

## Origin

One of the original Gestalt principles of perceptual grouping, described by Max Wertheimer in 1923 and developed with Kurt Koffka and Wolfgang Köhler in the early 20th century.

Cite as: Max Wertheimer, "Laws of organization in perceptual forms" (1923).
