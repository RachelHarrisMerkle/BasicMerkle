# Simon Effect

UX Theory card. Audit lens: Targets and movement.

Related cards in the deck: [Stroop Effect](stroop-effect.md), [Fitts' Law](fitts-law.md).

## In one line

People respond faster and more accurately when a signal appears in the same relative location as the response it calls for.

## What it asks of an interface

- Put a control where people expect its effect to happen. The action that adds an item to a list belongs at the point in the list where the item will appear.
- Position carries meaning. A control on the left that produces an effect on the right, or a "back" action on the forward side, causes hesitation and slips.
- Location should agree with direction, sequence and the content the control belongs to.

## When it applies

- Add, edit and delete actions on lists and tables; inline editing; previous and next; back and forward; pagination; dialogs and their buttons; split views.
- Notifications and errors: they should appear near what triggered them.

## Detect a violation

**In code**

- An "Add" control placed at the opposite end from where new items appear: new rows append at the bottom but the add button is at the top right, or the reverse, with no scroll to the new item.
- Row actions detached from their rows: actions for a selected item in a distant toolbar with no visible link to the row.
- Direction conflicts: "Back" or "Previous" on the right in a left-to-right layout, "Next" on the left, a carousel whose left arrow advances.
- In right-to-left locales, direction not mirrored (`dir="rtl"` unsupported, hard-coded `left` and `right` instead of logical properties).
- Feedback that appears far from the action: an error at the top of the page for a field at the bottom, a toast in the opposite corner from the control.
- Controls that change position between states: a button that swaps places with another after a click, or "Confirm" appearing where "Cancel" was.

**In a screenshot or design file**

- For each action, mark where the result will appear. A long distance between the two is a finding.
- Left and right placement of backward and forward controls.
- Consecutive screens of a flow: does the primary button stay in the same place?

## Example

**Bad:** A to-do list where new tasks appear at the bottom but the only "Add task" button is in the page header, and a wizard whose "Back" button sits to the right of "Next".

**Good:** An "Add task" row at the bottom of the list where the new task will land, and "Back" on the left with "Next" on the right, in the same positions on every step.

## When laws conflict

- Against Fitts' Law: put the control where the effect happens first. If that is hard to reach, add a second control at the convenient spot.
- Against Jakob's Law: platform conventions for button order in dialogs win over a local sense of direction.
- With Mapping: Mapping is about which control affects which thing; Simon is about where the response should sit relative to the signal. In practice both say "keep it local".

## Origin

From a 1967 study by J. Richard Simon and Alan Rudell. Participants heard the words "left" or "right" in one ear and pressed the matching key. Responses were slower when the word arrived in the ear opposite to the correct key, although ear position had nothing to do with the task.

Cite as: J. Richard Simon and Alan Rudell (1967).
