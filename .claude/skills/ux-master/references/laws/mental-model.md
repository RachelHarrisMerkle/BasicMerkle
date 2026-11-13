# Mental Model

Psychology Concept card. Audit lens: Expectations.

Related cards in the deck: [Jakob's Law](jakobs-law.md), [Conceptual Model](conceptual-model.md).

## In one line

A mental model is what a person believes about how something works, built from their past experience.

## What it asks of an interface

- People arrive with expectations. A design that matches them lets people reuse what they know and get straight to the task.
- A design that breaks a common expectation for the sake of novelty risks losing people, as with online stores that drop the familiar cart and checkout pattern.
- The team's own mental model of the product is not the user's. Closing that gap takes research: interviews, personas, journey maps.

## When it applies

- Structure and naming, core flows (sign up, search, buy, share, undo), anything with a strong convention.
- Redesigns, where existing users have a model built on the old version.

## Detect a violation

**In code**

- Core patterns rebuilt in an unusual way: a cart that is not called a cart or is not reachable from every page, search that does not run on Enter, a logo that does not link home, a modal that does not close on Escape.
- Navigation organized by the company's internal structure (team names, database entities) instead of the tasks people come to do.
- Terms taken from the codebase or the business in user-facing strings.
- A redesign that moves or renames core actions with no transition help: no pointer from the old place, no notice, no way back.
- Standard gestures or keys (swipe back, pull to refresh, Tab, Escape, Cmd or Ctrl plus Z) overridden or ignored.

**In a screenshot or design file**

- Compare the screen with the two or three most-used products of the same kind. List every structural difference and ask what the difference buys.
- Labels a newcomer would not recognize.
- A familiar-looking layout with familiar elements in unfamiliar positions.

## Example

**Bad:** A store that replaces the cart with a "Collection" drawer that opens from a custom icon, and removes the checkout button from product pages.

**Good:** A cart icon with a count in the top right of every page, a product page with one clear "Add to cart" button, and a checkout that follows the usual order: cart, details, payment, confirmation.

## When laws conflict

- Against Von Restorff Effect and brand distinctiveness: match the model for structure and behavior, and be distinctive in content, tone and visual style.
- Against the team's preference: when the team's model and the users' model differ, the users' model wins unless research shows theirs fails the task.
- With Jakob's Law: Jakob's Law is the rule of thumb; mental models are the reason behind it.

## Origin

The idea is usually traced to Kenneth Craik's 1943 book The Nature of Explanation, which proposed that people carry small-scale models of the world in their heads and use them to predict events. It has been central to human-computer interaction since the 1980s.

Cite as: Kenneth Craik, The Nature of Explanation (1943).
