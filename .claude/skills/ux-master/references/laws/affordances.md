# Affordances

Interaction Principle card. Audit lens: Signals and feedback.

Related cards in the deck: [Signifiers](signifiers.md), [Usability Test](usability-test.md).

## In one line

An affordance is an action that an object makes possible for a particular person. In an interface, the form of a control should suggest what you can do with it.

## What it asks of an interface

- People guess what a control does from its shape before they read anything. A raised, filled, bordered shape reads as pressable. Underlined colored text reads as a link.
- The affordance is the possible action. The signifier is the cue that tells people where that action is. A control needs both.
- An affordance only helps if it matches what the person expects that kind of object to do.
- False affordances are as harmful as missing ones: something that looks pressable and does nothing teaches people to distrust the screen.

## When it applies

- Every interactive element: buttons, links, inputs, toggles, sliders, drag handles, cards that open.
- Every non-interactive element that might be mistaken for one: badges, tags, headings, stat tiles.

## Detect a violation

**In code**

- Click or tap handlers on generic containers (`<div onClick>`, a tappable `View` or `Text`) with no button or link semantics and no pressed, hover or focus style.
- Elements styled as buttons (filled background, border radius, pointer cursor) that have no handler, or are disabled with no visual difference from enabled.
- Links styled as plain body text: no underline and the same color as surrounding text.
- Inputs with no border, background or underline, so they look like static text.
- Draggable items with no handle and no cursor or style change.
- `cursor: pointer` on things that do nothing, or default cursor on things that act.

**In a screenshot or design file**

- Cover the labels. Can you still tell which things are pressable, which are editable and which are static?
- Badges, pills or tags that share the exact shape and color of real buttons.
- Flat text that is the only way to trigger an action.
- Disabled controls that look the same as enabled ones, or enabled ones that look washed out.

## Example

**Bad:** A settings page where "Edit" is gray text with no underline next to gray helper text, and status badges are bright filled pills that look like the page's only buttons.

**Good:** "Edit" is a bordered button with a pressed state. Status badges are small, unfilled and non-interactive in appearance, so nothing invites a click that will not work.

## When laws conflict

- Against Aesthetic-Usability Effect (a cleaner, flatter look): affordance wins. A control that people cannot recognize as a control is a functional failure, however good it looks.
- Against Law of Similarity (make things consistent): interactive and non-interactive elements must not share a style. Consistency applies within each group, not across them.

## Origin

The word comes from perceptual psychologist James J. Gibson. Don Norman brought it into design in The Design of Everyday Things (1988) and later separated it from the signifier, the perceivable cue that points to the action.

Cite as: James J. Gibson coined the term (1966, 1979); Don Norman applied it to design in The Design of Everyday Things (1988).
