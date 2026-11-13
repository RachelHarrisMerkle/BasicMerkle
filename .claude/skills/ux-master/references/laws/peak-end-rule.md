# Peak-End Rule

UX Theory card. Audit lens: Progress and endings.

Related cards in the deck: [Jakob's Law](jakobs-law.md), [Cognitive Bias](cognitive-bias.md).

## In one line

People judge an experience mostly by how it felt at its most intense moment and at its end, not by the average of every moment.

## What it asks of an interface

- Find the most intense points of the journey, good and bad, and the final moment. These shape what people remember.
- Put care into the moments where the product is most useful, valuable or enjoyable.
- Negative peaks count too. One bad moment (an error that loses work, a failed payment with no way forward) can define the memory of the whole experience.
- The end is always reached, so it is the cheapest place to improve: confirmations, success screens, the last step of a flow.

## When it applies

- Checkout and payment confirmation, sign-up completion, task completion, cancellation, error recovery, the end of onboarding.
- Rare, significant moments. Not routine actions people repeat many times a day.

## Detect a violation

**In code**

- Success and confirmation states that are missing or bare: a redirect to the home page with no message, or a page that says only "Success".
- Confirmation with no next step and no record: no summary of what was done, no receipt or reference, no "what happens now".
- Error handling at the highest-stakes steps (payment, submit, upload) that loses the person's input or gives no way forward.
- Flows that end in a dead end: no link onward, no way back to where the person was.
- The last step of a flow is the heaviest: a surprise extra form, a forced survey or an upsell just before or after completion.
- Cancellation and off-boarding flows built to obstruct.

**In a screenshot or design file**

- Find the last screen of each flow. Does it confirm what happened, give something useful (a receipt, a next step) and close cleanly?
- Find the error states for the highest-stakes steps. Do they keep the person's work and offer a way forward?
- A final screen that looks unfinished compared with the rest.

## Example

**Bad:** After payment, the page reloads to the cart, now empty, with no confirmation. An email arrives minutes later.

**Good:** A confirmation screen with the order number, what was bought, when it will arrive, a link to track it and a clear primary action for what to do next.

## When laws conflict

- Against Doherty Threshold, Flow and Parkinson's Law: do not slow frequent tasks with celebration. Save designed moments for rare milestones.
- Against Cognitive Bias: a pleasant ending must not be used to cover a bad deal. The rule describes memory; it does not excuse the experience.
- Among negative peaks and positive ones: fix the negative peak first. Removing the worst moment usually changes the remembered experience more than adding a nice one.

## Origin

A 1993 study by Kahneman, Fredrickson, Schreiber and Redelmeier had participants hold a hand in 14 degree Celsius water for 60 seconds, and in another trial for the same 60 seconds plus 30 more while the water warmed to 15 degrees. Most chose to repeat the longer trial: it contained more discomfort in total, but it ended less badly.

Cite as: Daniel Kahneman, Barbara Fredrickson, Charles Schreiber and Donald Redelmeier, "When More Pain Is Preferred to Less: Adding a Better End", Psychological Science (1993).
