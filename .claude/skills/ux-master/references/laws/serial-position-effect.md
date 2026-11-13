# Serial Position Effect

UX Theory card. Audit lens: Focus.

Related cards in the deck: [Zeigarnik Effect](zeigarnik-effect.md), [Selective Attention](selective-attention.md).

## In one line

People remember the first and last items in a series best, and the middle ones least.

## What it asks of an interface

- The first items benefit from primacy and the last from recency.
- Put the most important items at the start and end of a list or bar.
- Put the least important items in the middle.
- In navigation, key actions at the far left and far right are the ones people learn fastest.

## When it applies

- Navigation bars, tab bars, menus, action lists, onboarding slides, pricing rows, the order of content on a page.
- Short sets that people take in as a series. In long searchable lists, and in lists with a natural order, order by that logic instead.

## Detect a violation

**In code**

- The most important or most used item sits in the middle of a navigation list, tab bar or button group. Check the order of nav children and tab definitions.
- Low-value items (legal links, rarely used tools) placed first or last in a primary bar.
- The primary action in the middle of a row of actions, not at the end the platform expects.
- The key message of a page in the middle of long content, with neither the opening nor the closing section stating it.
- Onboarding or carousel sequences where the most important slide is neither first nor last.

**In a screenshot or design file**

- For each horizontal or vertical series of five or fewer peers: what is first, what is last, and are those the items that matter most?
- Bottom tab bars on mobile: are the two edge positions and the center used for the most important destinations?
- Long pages: does the last screenful repeat the main action?

## Example

**Bad:** A five-item tab bar ordered Settings, Help, Home, Search, About, with the two most used destinations in the middle and second from the end.

**Good:** Home first, Search second, the primary action in the center, Activity fourth and Profile last, matching common platform order.

## When laws conflict

- Against Jakob's Law: where order is set by convention (Home first, account last, Cancel and OK in platform order) or by logic (alphabetical, chronological, numeric), that order wins.
- Against Pareto Principle: if the most used item cannot go first or last because of convention, give it visual emphasis instead.
- With Von Restorff Effect: position and distinctiveness are two ways to make an item memorable. Use one, not both, on the same item unless it is the single primary action.

## Origin

The term is credited to Hermann Ebbinghaus, whose memory experiments in the 1880s showed that recall depends on an item's position in a sequence. Bennet Murdock's 1962 free-recall studies mapped the familiar U-shaped curve of primacy and recency.

Cite as: Hermann Ebbinghaus (1885); Bennet Murdock (1962).
