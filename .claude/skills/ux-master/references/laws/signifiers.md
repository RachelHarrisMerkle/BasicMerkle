# Signifiers

Interaction Principle card. Audit lens: Signals and feedback.

Related cards in the deck: [Affordances](affordances.md), [Usability Test](usability-test.md).

## In one line

A signifier is any cue you can see or hear that tells you where an action happens and how to do it.

## What it asks of an interface

- Affordances say what is possible. Signifiers point at it. Labels, icons, arrows, underlines, placeholders, handles, chevrons and sounds are all signifiers.
- Without a signifier, people have to discover an affordance by accident.
- The most reliable signifier is a short text label. Icons alone work only for a small set of conventions.
- A signifier that points the wrong way is worse than none: a chevron on a row that does not expand, an arrow that suggests "forward" on a control that goes back.

## When it applies

- Icon buttons, form fields, expandable sections, carousels, scrollable regions, drag and drop, swipe actions.
- Anywhere content continues beyond what is visible.

## Detect a violation

**In code**

- Icon-only controls with no visible label and no tooltip. Check every `<button>` or tappable whose only child is an icon or SVG.
- Form fields with no persistent label. The placeholder is used as the label, so it disappears on input. Look for inputs with `placeholder` and no associated `<label>`, `aria-label` or visible text.
- Expandable regions (accordion, disclosure, dropdown) with no chevron, plus sign or state change between open and closed.
- Scrollable containers with hidden scrollbars and no cut-off content, fade or arrow to show there is more.
- Required and optional fields that are not marked.
- Links whose text is "click here" or "learn more" with nothing saying where they lead.

**In a screenshot or design file**

- Any icon whose meaning you cannot name with confidence without hovering.
- Fields that look empty and unlabeled once filled.
- A row of items that ends exactly at the container edge, hiding that it scrolls.
- Chevrons, arrows or carets that suggest an interaction the element does not have.

## Example

**Bad:** A toolbar of six unlabeled line icons, two of which are near-identical, and a form whose only labels are placeholders that vanish as soon as you type.

**Good:** The toolbar shows icon plus one-word label for each action. Every field has a label above it that stays visible, with example text shown as a hint below.

## When laws conflict

- Against Occam's Razor and Law of Prägnanz (remove visual elements): a label that tells people what a control does is not clutter. Text labels win over minimal icon-only layouts unless the icon is a true convention.
- Against Law of Closure (let people fill in the rest): closure can simplify an icon, but it cannot explain it. When an icon carries an important or irreversible action, add the label.

## Origin

Don Norman introduced the term to separate the cue from the action it points to, most fully in the 2013 revised edition of The Design of Everyday Things. It is one of the concepts he lists as producing discoverability.

Cite as: Don Norman, The Design of Everyday Things (revised edition, 2013).
