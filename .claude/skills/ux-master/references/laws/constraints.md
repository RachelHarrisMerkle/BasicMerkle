# Constraints

Interaction Principle card. Audit lens: Input and recovery.

Related cards in the deck: [Cognitive Load](cognitive-load.md), [Usability Test](usability-test.md).

## In one line

Constraints limit what people can do so that the right action is the easy one and the wrong action is hard or impossible.

## What it asks of an interface

- Norman names four kinds. Physical constraints make an action impossible (a control that cannot move past its limit). Semantic constraints rely on meaning (it only makes sense one way). Cultural constraints rely on shared convention. Logical constraints rely on reasoning (one item left, one slot left).
- Fewer possible actions means fewer errors and less to think about.
- A good constraint is visible before the action, not announced after it as an error message.

## When it applies

- Forms and inputs with a known set of valid values: dates, quantities, choices, file types.
- Steps that only make sense in order.
- Destructive or irreversible actions.
- Do not over-apply: constraining the format of free text people type (phone numbers, names, card numbers) creates errors instead of preventing them. See Postel's Law.

## Detect a violation

**In code**

- Free-text inputs for values that come from a small known set (country, plan, state, yes or no). A select, radio group or segmented control would remove invalid input.
- Date, time, quantity or range inputs with no `min`, `max` or `step`, where the valid range is known.
- Wrong input type or keyboard: `type="text"` for email, number, phone or URL; no `inputmode` or `autocomplete`; no equivalent keyboard type on native.
- Submit or next actions that are enabled when required input is missing and then fail, or actions that should be unavailable in the current state but are still clickable.
- Steps in a flow that can be opened out of order when order matters.
- Irreversible actions (delete, send, pay) with no confirmation step and no undo.
- Validation rules that exist only on the server, so the first sign of a problem is a round trip.

**In a screenshot or design file**

- Open text boxes for things with a fixed set of answers.
- No visible limits on ranges: sliders with no end labels, date fields with no hint of the allowed period.
- A destructive button sitting right beside the primary button with the same emphasis.
- Later steps of a flow look available when earlier ones are incomplete.

## Example

**Bad:** A booking form with a free-text "Date" field that accepts any string and reports "Invalid date" after submit, and a "Delete workspace" button that acts immediately.

**Good:** A date picker that only offers dates that can be booked. "Delete workspace" opens a dialog that names the workspace and what will be lost, with Cancel as the default.

## When laws conflict

- Against Postel's Law (accept anything): they cover different things. Constrain the choice when the valid set is known. Be liberal with the format when people type. A date picker and a phone field that accepts spaces are both correct.
- Against Flow (do not interrupt): confirmation dialogs are constraints with a cost. Use them for irreversible, high-cost actions only. For everything else prefer undo.
- Against Hick's Law: constraints help it. Removing invalid options is the cheapest way to shorten a decision.

## Origin

One of Don Norman's fundamental principles of interaction. The four categories (physical, cultural, semantic and logical) come from The Design of Everyday Things.

Cite as: Don Norman, The Design of Everyday Things (1988, revised 2013).
