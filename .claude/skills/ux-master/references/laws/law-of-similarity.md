# Law of Similarity

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Law of Proximity](law-of-proximity.md), [Selective Attention](selective-attention.md).

## In one line

Things that look alike are seen as related, even when they are apart.

## What it asks of an interface

- Shared color, shape, size, orientation or movement tells people that elements belong to one group and probably do the same kind of thing.
- So elements with the same function should look the same, and elements with different functions should look different.
- Links and navigation should be visibly different from ordinary text.

## When it applies

- Buttons by role (primary, secondary, destructive), links, icons, tags and statuses, navigation, form controls, headings by level.
- Consistency across screens: the same thing should look the same everywhere.

## Detect a violation

**In code**

- One role, several styles: primary buttons with different colors, sizes or radii across a screen or flow; links that are underlined in one place and not in another. Search the styles for near-duplicate button and link rules.
- Several roles, one style: primary, secondary and destructive actions sharing a class or variant; interactive text styled the same as body text; headings the same size as body.
- Color used for more than one meaning: the brand color on both links and non-interactive headings, red for both errors and a sale badge.
- Status indicators (success, warning, error) that differ only slightly, or the same status shown differently in two places.
- Icons from mixed sets or at mixed weights within one group.
- Similar-looking items that behave differently: some cards in a grid open on click and others do not.

**In a screenshot or design file**

- Group elements by appearance. Does each visual group map to one function?
- Group elements by function. Does each function have one appearance?
- Body text and links that cannot be told apart without hovering.

## Example

**Bad:** A page where the brand blue is used for links, section headings and decorative icons, and the two "Save" buttons on different tabs are different sizes.

**Good:** Blue means "clickable" everywhere and nothing else. Every primary button uses the same variant.

## When laws conflict

- Against Von Restorff Effect: similarity is the rule and Von Restorff is the single exception. One element per view may break the pattern to draw attention. If several do, none stands out.
- Against Affordances: never let interactive and static elements share a look for the sake of consistency.
- Against Stroop Effect: similarity must follow meaning. Two opposite actions (confirm and cancel) must not look the same.

## Origin

One of the original Gestalt grouping principles described by Max Wertheimer in 1923 and developed with Kurt Koffka and Wolfgang Köhler.

Cite as: Max Wertheimer, "Laws of organization in perceptual forms" (1923).
