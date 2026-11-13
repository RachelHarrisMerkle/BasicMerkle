# Hick's Law

UX Theory card. Also called: Hick-Hyman Law. Audit lens: Choice and load.

Related cards in the deck: [Fitts' Law](fitts-law.md), [Cognitive Load](cognitive-load.md).

## In one line

The more options there are, and the more complex they are, the longer a decision takes.

## What it asks of an interface

- Cut the number of choices where speed matters.
- Break a complex task into smaller steps so each step is a small decision.
- Recommend an option so people do not have to weigh every one.
- Introduce features gradually to new users instead of showing everything on first use.
- Do not simplify until meaning is lost. Vague labels and icon-only menus make each choice harder, which defeats the purpose.

## When it applies

- Decision points: pricing tiers, navigation menus, action bars, dialogs, first-run choices, "what do you want to do" screens.
- The original finding is about choosing among simple, equally likely options, and decision time grows with the logarithm of the number of options. It does not predict how long people take to read a long unfamiliar list, and it gives no magic maximum number.
- Less relevant when people already know what they want and the list is ordered so they can find it (alphabetical countries, for example).

## Detect a violation

**In code**

- Count sibling options at each decision point: plan cards, top-level nav items, buttons in one toolbar or dialog, radio options, tabs. No research gives a hard cap. As a working heuristic, treat more than about 5 to 7 equal-weight, ungrouped options as a prompt to look for grouping, a default or a recommendation.
- Several primary-styled actions in one view (more than one filled, high-emphasis button competing).
- Choice sets with no default selection and no recommended option.
- Dialogs with three or more actions of equal weight.
- First-run screens that expose every feature or setting at once.
- Long flat menus with no groups, separators or search.
- Over-simplification: hamburger or "More" menus hiding primary navigation on wide screens, or icon-only choices with no labels.

**In a screenshot or design file**

- At each point where the person must choose, count the choices and ask which one the design suggests.
- Rows of identical cards or buttons with nothing marked as the usual choice.
- Menus that fill the screen.

## Example

**Bad:** A pricing page with seven plans, all styled the same, and a header with twelve top-level navigation links.

**Good:** Three plans with one recommended, a link to "Compare all plans", and navigation grouped into five labeled sections.

## When laws conflict

- Against Tesler's Law: never remove an option the task needs. Reduce the options visible at each step and let defaults and disclosure carry the rest.
- Against Discoverability: for frequent actions, visible wins even if the count goes up. For rare actions, tucked away wins.
- Against Principle of Least Effort and Fitts' Law (fewer clicks): several easy decisions usually beat one hard decision. Split into steps when each step is a real decision; do not split a simple form into pages just to lower the count per page.
- Against Miller's Law: do not quote "seven" as a limit for menus. A visible menu is read, not remembered.

## Origin

Named for British psychologist William Edmund Hick and American psychologist Ray Hyman, whose experiments in 1952 and 1953 measured how reaction time rises with the number of possible stimuli. The relationship they found is logarithmic.

Cite as: William Edmund Hick (1952) and Ray Hyman (1953).
