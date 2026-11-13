# Law of Uniform Connectedness

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Law of Common Region](law-of-common-region.md), [Selective Attention](selective-attention.md).

## In one line

Elements that are visually connected are seen as more related than elements that are not.

## What it asks of an interface

- A line, arrow, shared color band or frame that links elements makes them read as one unit.
- Use a connection to show sequence (steps), dependency (this controls that) or membership (these belong together).
- Connection is one of the strongest grouping cues. A line between two things beats distance and difference in style.

## When it applies

- Steppers and progress trackers, timelines, tree views and nested lists, flow diagrams, breadcrumbs, tabs and their panels, form fields joined to one another (a range's start and end), input groups with attached buttons.

## Detect a violation

**In code**

- Steps in a flow rendered as separate items with no connecting line or bar, so they read as unrelated badges instead of a sequence.
- A tab that is not visually joined to its panel: a gap or border between the active tab and the content it controls.
- Nested or threaded content (replies, sub-tasks, tree nodes) indented with no guide line, where depth is hard to follow.
- Paired inputs (start and end date, minimum and maximum) rendered as two unrelated fields with no joining label or connector.
- A dropdown, popover or tooltip that opens detached from its trigger with no pointer or alignment.
- Connections that are wrong: a divider or line that visually joins unrelated items, or a continuous bar that links actions belonging to different objects.

**In a screenshot or design file**

- Sequences that are not drawn as sequences.
- Lines, arrows or shared bands: for each, check that what it joins is related.
- Floating menus or panels with no visible link to what opened them.

## Example

**Bad:** A four-step checkout shown as four separate gray circles with labels and nothing joining them, and an active tab separated from its panel by a full border.

**Good:** The four steps sit on one line that fills as steps are completed. The active tab shares a background with its panel and has no border between them.

## When laws conflict

- Against Law of Prägnanz and Occam's Razor (fewer marks on screen): add a connector when order or dependency matters to the task and spacing does not show it. Otherwise leave it out.
- Against Law of Proximity and Law of Similarity: connection is stronger. A stray line will group things you did not mean to group, so remove connectors that are decorative.

## Origin

Proposed by Stephen Palmer and Irvin Rock in 1994 as an addition to the classic Gestalt grouping principles of Wertheimer, Koffka and Köhler. They argued that connected regions of uniform visual properties are perceived as single units before other grouping takes place.

Cite as: Stephen Palmer and Irvin Rock, "Rethinking perceptual organization: The role of uniform connectedness", Psychonomic Bulletin and Review (1994).
