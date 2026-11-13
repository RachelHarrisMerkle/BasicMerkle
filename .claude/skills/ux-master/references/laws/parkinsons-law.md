# Parkinson's Law

UX Theory card. Audit lens: Choice and load.

Related cards in the deck: [Pareto Principle](pareto-principle.md), [Flow](flow.md).

## In one line

Work expands to fill the time available for it.

## What it asks of an interface

- People arrive with an expectation of how long a task should take. Keep the task within that expectation.
- Beating the expected time makes the experience feel better.
- Remove work that inflates the task. Autofill, saved details and sensible defaults let people finish purchases, bookings and forms quickly.
- Open-ended tasks drift. Clear scope and a visible end keep them short.

## When it applies

- Forms, checkout, booking, sign-up, any data entry.
- Tasks with a natural time expectation: "quick" actions, mobile tasks, anything described as taking a minute.
- Also applies to the team: design reviews and audits without a time limit expand too.

## Detect a violation

**In code**

- Form fields missing `autocomplete` attributes (name, email, tel, address parts, `cc-number`, `one-time-code`) or the native equivalents, so browsers and password managers cannot fill them.
- Known information asked for again: details the account already holds, a billing address when "same as shipping" would do, a country that could be inferred and offered as the default.
- No sensible defaults on selects, dates or quantities.
- Paste disabled on any field.
- No saved progress: a long form that loses everything on refresh, back or timeout.
- Open text areas with no guidance on expected length where a short answer is wanted.
- Flows that promise a duration ("Takes 2 minutes") and contain far more than that.

**In a screenshot or design file**

- Estimate the time to complete the screen for a first-time visitor. Compare with what the entry point promised.
- Fields the product could have filled in.
- Free-text boxes with no hint of how much to write.

## Example

**Bad:** A "quick checkout" that asks returning customers to retype name, address and card, with autofill blocked and paste disabled on the email confirmation field.

**Good:** Saved details pre-filled and editable, correct `autocomplete` values on every field, one email field, and an express payment option.

## When laws conflict

- Against Peak-End Rule and Goal-Gradient Effect: do not lengthen a task to add a pleasant moment or a sense of progress. Shorter wins.
- Against Constraints and security prompts: necessary checks stay, but each must justify the time it costs.
- Against Hick's Law (splitting into steps): splitting is fine if total time does not grow. Measure the whole task, not each page.

## Origin

Stated by naval historian Cyril Northcote Parkinson in the opening line of a satirical essay in The Economist in 1955, drawn from his experience of the British Civil Service, and later published in the book Parkinson's Law.

Cite as: Cyril Northcote Parkinson, The Economist (1955).
