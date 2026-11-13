# Mapping

Interaction Principle card. Audit lens: Signals and feedback.

Related cards in the deck: [Conceptual Model](conceptual-model.md), [Usability Test](usability-test.md).

## In one line

Mapping is the relationship between a control and the thing it changes. Good mapping makes that relationship obvious from layout and direction.

## What it asks of an interface

- When controls are arranged the way the things they control are arranged, people do not need labels to work out which is which.
- Natural mapping uses spatial sense: up or right for more, down or left for less, a control placed next to its effect.
- Poor mapping forces people to learn by trial and error and to remember the result.

## When it applies

- Toggles, sliders, steppers, sort and filter controls, settings that affect a preview, editors with a canvas and a property panel.
- Any control that is visually separated from what it changes.
- Directional controls: arrows, carousels, pagination, back and forward.

## Detect a violation

**In code**

- Controls placed in a different container from their effect with nothing linking them: a filter bar that changes a list several sections away, a "Save" button in a header that saves a form far below.
- Controls ordered differently from the things they control (three columns, but their three toggles listed in another order).
- Sliders or steppers whose value decreases to the right or upward, or whose plus and minus are reversed.
- Toggles where the label describes the off state, or where it is unclear whether the label names the current state or the action ("Notifications off").
- Carousels or pagers whose previous and next arrows are on the unexpected sides or move content in the opposite direction.
- Keyboard arrow handling that moves selection against the visual layout.

**In a screenshot or design file**

- For each control, draw an imaginary line to what it changes. Long lines, crossing lines or lines to off-screen elements are findings.
- A grid of items with controls laid out in a different order or orientation.
- Toggles with ambiguous state: can you tell on from off without clicking?

## Example

**Bad:** A dashboard with four chart cards in a 2 by 2 grid and a single row of four unlabeled "eye" toggles in the page header that show or hide them, in a different order.

**Good:** Each chart card has its own show or hide control in its own header. A slider for font size sits directly above the live preview text and grows it as it moves right.

## When laws conflict

- Against Fitts' Law (put controls where they are fastest to reach): place the control next to its effect first. If that makes it hard to reach, repeat it, but do not move the only copy away from what it controls.
- Against Jakob's Law (follow convention): where a platform convention fixes a control's place (back at top left, primary action at bottom right in dialogs on some platforms), the convention wins and you make the relationship clear with labels.

## Origin

Norman borrowed the term from mathematics, where it names the relationship between the elements of two sets. In The Design of Everyday Things he uses stove burners and their knobs as the classic example of good and bad mapping.

Cite as: Don Norman, The Design of Everyday Things (1988, revised 2013).
