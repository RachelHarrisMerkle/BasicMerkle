# Law of Continuity

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Selective Attention](selective-attention.md).

## In one line

Elements arranged along a line or curve are seen as related and are followed by the eye in that direction.

## What it asks of an interface

- Alignment creates a path. People read along it and treat what sits on it as one series.
- Use alignment to lead people through a screen: fields down one edge, steps along one line, cards along one row.
- Break the line on purpose to show that something new begins. A divider, an offset or a change of direction signals a new section.
- An accidental break does the same thing, so misalignment reads as "this is separate" even when it is not.

## When it applies

- Forms, lists, tables, navigation bars, timelines, steppers, card rows, reading order on a page.
- Charts and diagrams where lines are followed across intersections.

## Detect a violation

**In code**

- Siblings that should align but do not: labels and fields with different left edges, buttons at different baselines, cards with different top offsets. Look for one-off margins, paddings and transforms on individual siblings.
- Form fields laid out in an irregular grid (some full width, some half, some thirds) so there is no single line to follow downward.
- Multi-column forms where the reading order zigzags and tab order does not match the visual order.
- No visual break between sections: one unbroken column for unrelated groups.
- A break where none is meant: an indent, divider or offset in the middle of a single group.
- Visual order that differs from source or focus order (`order`, absolute positioning, `tabindex` greater than zero), so the eye follows one path and the keyboard another.

**In a screenshot or design file**

- Draw a line down the left edge of the content. Count how many elements sit off it without a reason.
- Follow the natural reading path. Does it pass through the important things in the right order?
- Places where a new section starts with no visible break.

## Example

**Bad:** A sign-up form with first name and last name side by side, then a full-width email, then three uneven columns for password, confirm and a checkbox, with the submit button centered below.

**Good:** One column, every label and field on the same left edge, the button on that edge too, and a clear gap and heading where the billing section begins.

## When laws conflict

- Against density (two or more columns to save height): a single column wins for forms that are filled in top to bottom. Use columns only for fields that are read as one unit, such as city, state and postal code.
- Against Von Restorff Effect: break alignment for one element only if it is the thing you want noticed.
- With Law of Proximity: alignment says "these form a series"; spacing says "these form a group". Use both.

## Origin

One of the original Gestalt grouping principles, described by Max Wertheimer in 1923 as "good continuation": elements that follow a smooth line or curve are perceived as belonging together.

Cite as: Max Wertheimer, "Laws of organization in perceptual forms" (1923).
