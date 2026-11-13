# Accot-Zhai Steering Law

UX Theory card. Also called: The Steering Law. Audit lens: Targets and movement.

Related cards in the deck: [Fitts' Law](fitts-law.md), [Cognitive Load](cognitive-load.md).

## In one line

The time it takes to steer a pointer or finger through a path depends on how long and how narrow the path is. Long, narrow paths are slow and easy to fall out of.

## What it asks of an interface

- Steering along a long straight line is physically hard for wrists and elbows. The longer the movement, the more likely an error.
- Keep any path the pointer must follow as short and as wide as possible. This covers dropdowns, nested menus, sliders and anything dragged.
- Avoid nested menus more than two levels deep.
- Use a short delay before a submenu opens or closes, and allow diagonal movement from a parent item to its submenu, so a slight wobble does not dismiss it.

## When it applies

- Hover-driven cascading menus and mega menus, sliders and range inputs, scrubbers, drag and drop, drawing or cropping handles, scrollbars, swipe gestures along an axis.
- Mostly pointer and touch. Keyboard access removes the steering problem, which is one more reason to provide it.

## Detect a violation

**In code**

- Nested menus three or more levels deep.
- Submenus opened on `:hover` or `mouseenter` and closed immediately on `mouseleave`, with no delay and no tolerance for diagonal movement toward the submenu.
- Menu rows that are narrow in the steering direction: short row height in a long vertical menu the pointer must travel down before moving sideways.
- Sliders with a thin track and small thumb, or a wide value range on a short track so tiny movements matter. No text input or stepper offered as an alternative.
- Drag and drop as the only way to reorder or move items, with small drop zones or long distances and no keyboard or button alternative.
- Hover-revealed controls that disappear when the pointer leaves a thin strip.
- Custom thin scrollbars as the only way to scroll a region.

**In a screenshot or design file**

- Trace the pointer path for each menu, slider and drag action. Mark any long, narrow corridor.
- Menus that cascade more than two levels.
- Sliders used for precise values with no numeric field beside them.

## Example

**Bad:** A three-level hover menu where moving diagonally from "Products" toward its submenu crosses "Pricing" and closes it.

**Good:** A two-level menu that opens on click or after a short hover delay, keeps the submenu open while the pointer moves toward it, and has rows tall enough to track easily.

## When laws conflict

- Against Hick's Law (shorter menus through nesting): two levels at most. If the structure needs more, widen the first level with grouping, or move to a page or search.
- Against density: path-following controls need more room than point-and-click ones. Give sliders and submenus the space.
- With Fitts' Law: Fitts covers reaching a target; the Steering Law covers staying on a path to it. Check both for menus.

## Origin

Johnny Accot and Shumin Zhai derived the steering law from Fitts' law in 1997 and verified it experimentally for human-computer interaction. Similar laws had been found independently by Rashevsky (1959) and Drury (1971). For a straight tunnel, steering time grows with its length divided by its width.

Cite as: Johnny Accot and Shumin Zhai (1997).
