# Chunking

Psychology Concept card. Audit lens: Choice and load.

Related cards in the deck: [Miller's Law](millers-law.md), [Mapping](mapping.md).

## In one line

Chunking is breaking information into pieces and grouping the pieces into meaningful units, so people handle a few groups instead of many items.

## What it asks of an interface

- People scan before they read. Visible groups with clear headings let them find the part that matches their goal.
- Grouping shows relationships: what belongs together, what is more important, what comes next.
- Chunking does not reduce the content. It reduces the number of things people have to track at once.
- Use hierarchy inside each chunk: a heading, then the detail.

## When it applies

- Long forms, long pages, settings, tables with many columns, navigation with many items.
- Strings people read, type or check: phone numbers, card numbers, codes, IDs.
- Does not mean every group must hold a set number of items. Group by meaning.

## Detect a violation

**In code**

- Long runs of sibling elements with no grouping: many inputs in a row with no `<fieldset>`, section heading or step; many nav items with no group labels or separators; many table columns with no grouping.
- Long strings rendered or requested unformatted: a 16-digit card number, an IBAN, a license key or a one-time code as one unbroken run.
- Text walls: paragraphs with no headings, lists written as sentences.
- Headings that skip levels or are all the same level, so structure is flat.
- Lists longer than a screen with no categories, filtering or search.

**In a screenshot or design file**

- Count the distinct groups you can see without reading. If the answer is "one", the content is not chunked.
- Whitespace between groups is the same as whitespace within groups.
- Long numbers shown without spacing.
- Sections with no headings.

## Example

**Bad:** A 22-field account form in a single column with equal spacing, and a card number field that shows 4242424242424242.

**Good:** The form split into "Your details", "Company" and "Billing", each with a heading. The card number is displayed as 4242 4242 4242 4242 while still accepting any spacing on input.

## When laws conflict

- Against Law of Proximity and Law of Common Region: these are how you show chunks. Use spacing first and add borders or backgrounds only when spacing alone is ambiguous.
- Against Principle of Least Effort (fewer steps): chunking into steps adds clicks. Split into steps when the chunks are separate decisions; keep one page with visible sections when they are parts of one decision.
- Against Miller's Law misuse: do not cut content to hit a number. Group it.

## Origin

The term comes from George A. Miller's 1956 paper on the limits of short-term memory, which observed that people can hold more information when they recode it into larger meaningful units.

Cite as: George A. Miller, "The Magical Number Seven, Plus or Minus Two", Psychological Review (1956).
