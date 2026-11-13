# Discoverability

Interaction Principle card. Audit lens: Focus.

Related cards in the deck: [Conceptual Model](conceptual-model.md), [Usability Test](usability-test.md).

## In one line

People can work out what a product does, how it works and what they can do next by looking at it.

## What it asks of an interface

- Discoverability is an outcome, not a single control. It comes from getting five things right together: affordances, signifiers, constraints, mapping and feedback, held together by a clear conceptual model.
- A screen needs a focal point. Give the most important action visual priority and keep navigation where people look for it.
- Discoverability is different from findability. Findability is locating something you already know exists. Discoverability is learning that something exists at all.
- Use icons whose meaning is widely shared. Anything else needs a text label.

## When it applies

- Every screen with an action to take, and most of all first-run screens, empty states, toolbars and settings.
- Any feature reached through a gesture, a hover, a right-click, a keyboard shortcut or an overflow menu.
- Not a reason to show everything at once. Rare features need to be findable from a predictable place, not prominent.

## Detect a violation

**In code**

- An action exists only behind hover, right-click, long-press, swipe or a keyboard shortcut, with no visible control for it. Look for `:hover`-only reveals, `onContextMenu`, gesture recognizers and key handlers that have no matching button or menu item.
- The primary action of the screen sits inside an overflow menu (`...`, "More", kebab) or below a collapsed section.
- Icon-only buttons with no visible text and no accessible name (`aria-label`, `accessibilityLabel`, `contentDescription`).
- An empty state renders nothing, or only "No items", with no control that starts the first task.
- Navigation that appears only after scrolling or only at one breakpoint.

**In a screenshot or design file**

- Ask "what can I do here?" and try to answer from the pixels alone in five seconds. If the main action is not among the first things you notice, flag it.
- No element is visually dominant, or several are equally dominant.
- Rows or cards that turn out to be clickable but look like static content.
- Icons with no labels where the meaning is not a near-universal convention (search, close, home, back are safe; most others are not).

## Example

**Bad:** A project list where rename, duplicate and archive appear only on hover over a row, so touch users and first-time users never see them.

**Good:** Each row shows a labeled "Open" action and a visible "More" button that lists rename, duplicate and archive. Hover adds nothing that is not already reachable.

## When laws conflict

- Against Hick's Law and Occam's Razor (fewer things on screen): discoverability wins for actions people need often or need first. Reduce what is prominent, but keep frequent actions visible. Hiding wins only for rare actions, and then they go in one predictable place.
- Against Selective Attention (avoid distraction): make the current task's actions prominent and everything else findable. Findable is enough for secondary features.
- Against the Paradox of the Active User: never solve discoverability with an upfront tour. Solve it on the screen itself.

## Origin

One of Don Norman's fundamental principles of interaction, set out in The Design of Everyday Things (1988, revised 2013). Norman describes discoverability as the result of applying affordances, signifiers, constraints, mapping and feedback well, with the conceptual model tying them together.

Cite as: Don Norman, The Design of Everyday Things (1988, revised 2013).
