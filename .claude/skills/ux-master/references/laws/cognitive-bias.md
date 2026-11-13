# Cognitive Bias

Psychology Concept card. Audit lens: Honesty.

Related cards in the deck: [Peak-End Rule](peak-end-rule.md), [Conceptual Model](conceptual-model.md).

## In one line

Cognitive biases are predictable errors in judgment that come from the mental shortcuts people use to decide quickly.

## What it asks of an interface

- Shortcuts are useful. They let people act without analyzing everything. They also bend decisions in ways people do not notice.
- Biases work on the people building the product too. Confirmation bias, for example, makes a team notice the evidence that supports the design it already likes.
- Knowing about a bias does not remove it, but it lets you look for it and check your reasoning.
- In an interface, a bias can be used to help someone reach their own goal (a sensible default) or to push them toward yours (a pre-checked upsell). The first is design. The second is a dark pattern.

## When it applies

- Defaults, pre-selected options, recommended plans, anchoring prices, scarcity and urgency messages, social proof, opt-outs, cancellation flows.
- Design reviews and research synthesis, where the team's own biases are the risk.

## Detect a violation

**In code**

- Pre-checked boxes that add cost, share data or subscribe people to something. Look for `checked`, `defaultChecked` or a default `true` on optional paid or consent options.
- Countdown timers or "only 2 left" messages that are not backed by real data: a timer that resets on reload, a stock count that is a constant.
- Decline options written to shame ("No thanks, I don't want to save money").
- Accept and decline given unequal weight for a consent or cancellation choice: one a filled button, the other small low-contrast text.
- A default that benefits the business and is hard to change later.
- Prices shown without required fees until the final step.

**In a screenshot or design file**

- Any place where the choice the business prefers is visually louder than the alternative for a consent, privacy, cancellation or payment decision.
- Urgency, scarcity or social proof messages with no visible source.
- Crossed-out "original" prices with no stated basis.

## Example

**Bad:** A checkout with a pre-checked "Add 3-year protection" box, a 10-minute countdown that restarts on refresh, and a gray "No, I'll risk it" link under a large "Protect my order" button.

**Good:** Add-ons unchecked by default with a plain description and price. No timer. "Add protection" and "Continue without" are both clear buttons.

## When laws conflict

- Against every persuasion-friendly reading of another law (Goal-Gradient "artificial progress", Von Restorff emphasis, Peak-End): help people reach their own goal. If a technique only works when the person does not notice it, do not use it.
- Against conversion metrics: see Campbell's Law. A number that goes up because people were misled is not a design success.

## Origin

Amos Tversky and Daniel Kahneman introduced the modern study of cognitive biases in the early 1970s, showing through repeatable experiments that human judgment departs from the predictions of rational choice theory in systematic ways.

Cite as: Amos Tversky and Daniel Kahneman, work on heuristics and biases from the early 1970s.
