# The Principle of Least Effort

UX Theory card. Also called: Zipf's Principle of Least Effort. Audit lens: Choice and load.

Related cards in the deck: [Pareto Principle](pareto-principle.md), [Cognitive Load](cognitive-load.md).

## In one line

People take the path that costs them the least mental and physical effort to get the job done.

## What it asks of an interface

- People choose the easiest route available, and they stop as soon as they find something good enough.
- Show, do not tell. When something needs explaining, demonstrate it with an example or by highlighting the relevant element instead of describing it in text.
- Use progressive disclosure. Show a little, and let people open more if they want it. The less there is to process, the faster people find what they need.
- Ask only for what is necessary. People experience every requested field as something slowing them down.

## When it applies

- Sign-up and log-in, checkout, forms of every kind, onboarding, search, content pages, settings.
- Any step where people can leave instead of finishing.

## Detect a violation

**In code**

- Fields that are not needed to complete the task at this point: phone number on a newsletter sign-up, company size on a trial, date of birth with no stated reason. For each field ask what breaks if it is removed or asked later.
- Optional fields mixed in with required ones and not marked.
- Duplicate entry: "Confirm email", "Confirm password" with no show-password toggle, address typed twice.
- Account creation required before the person has received any value, where a guest path could exist.
- Long content shown in full where a summary with "Show more" would serve most readers.
- Explanatory paragraphs where an example, default value or inline preview would show the same thing.
- More steps or clicks for the common path than for a rare one.
- The easiest visible path leads to the wrong outcome: the most prominent button is not the one most people need.

**In a screenshot or design file**

- Count the inputs. For each one, name the reason it is needed now.
- Count the steps on the main path.
- Text that explains what could be shown.

## Example

**Bad:** A free trial sign-up asking for first name, last name, work email, phone, company, role, team size, country and password twice.

**Good:** Email and password with a show-password toggle. Everything else is asked later, in context, when it is needed.

## When laws conflict

- Against Hick's Law and Chunking (split into steps): fewer steps is not always less effort. Several easy steps can cost less than one dense screen. Minimize total effort, not click count.
- Against Constraints, security and legal requirements: required stays required. Explain in a few words why it is needed.
- Against Discoverability: progressive disclosure must leave a visible, labeled way in. Hidden with no cue is not disclosure.
- Against business requests for more data: each extra field needs a reason that is worth losing some of the people who would have finished without it.

## Origin

Proposed by Harvard linguist George Kingsley Zipf in his 1949 book Human Behavior and the Principle of Least Effort, which grew out of his statistical study of word frequency. It has since been applied widely, including to how people seek information.

Cite as: George Kingsley Zipf, Human Behavior and the Principle of Least Effort (1949).
