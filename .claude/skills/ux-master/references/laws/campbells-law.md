# Campbell's Law

UX Theory card. Audit lens: Honesty.

Related cards in the deck: [Pareto Principle](pareto-principle.md), [Cognitive Bias](cognitive-bias.md).

## In one line

The more a number is used to make decisions, the more people will bend their behavior to move the number, and the less the number tells you.

## What it asks of an interface

- When success is defined by a metric, people optimize for the metric, sometimes with results that hurt the experience the metric was meant to reflect.
- Use data to inform decisions. Do not let a single number make them.
- No metric describes the whole picture, and every metric reflects a choice about what counts.
- Pair numbers with qualitative evidence (interviews, usability tests, support conversations) so the consequences that analytics miss can be seen.

## When it applies

- Design goals and success criteria, A/B tests, dashboards the team is judged by, growth and engagement features.
- Reviews of interface choices that exist to move a number: forced sign-up, extra notifications, obstructed cancellation.
- Also applies to this bundle's own audit score. The score is a summary. The findings are the substance.

## Detect a violation

**In code**

- Interface choices whose only purpose is a metric: a mandatory account before any value is delivered, notifications on by default, an "Are you sure?" chain on cancel or unsubscribe, autoplay to raise watch time, infinite scroll with no end point where people came for a specific item.
- Engagement mechanics (streaks, badges, counters) attached to actions that do not help the person.
- Analytics events that measure activity (clicks, time on page) with nothing that measures whether the task was completed.
- An experiment with one success metric and no guardrail metric, such as conversion with no refund, complaint or retention measure.
- In a spec or pull request: a change justified by a single number with no user evidence.

**In a screenshot or design file**

- Elements that serve the business's dashboard more than the person's task.
- Friction placed on exits (cancel, unsubscribe, delete account) and removed from entries.
- A design rationale that cites one metric only.

## Example

**Bad:** A "time in app" target leads to a feed with no end and an unsubscribe link that opens a five-step survey.

**Good:** The target is "people who found what they came for", checked with a task-completion event and a short usability test. Unsubscribe takes one click.

## When laws conflict

- Against any metric-led argument for a design that harms the task: the task wins. Ask what the metric was standing in for and measure that more directly.
- Against Pareto Principle: focusing on what matters most is sound, but "matters" should be defined by people's goals as well as by the numbers that are easy to collect.
- With Cognitive Bias: both guard against designing for the business's view of success at the user's expense.

## Origin

Formulated by psychologist and social scientist Donald T. Campbell in the 1970s: the more a quantitative social indicator is used for decision-making, the more it is subject to corruption pressures and the more it distorts the processes it was meant to monitor. It is closely related to Goodhart's law in economics.

Cite as: Donald T. Campbell, "Assessing the Impact of Planned Social Change" (1976).
