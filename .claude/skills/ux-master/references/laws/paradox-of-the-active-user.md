# Paradox of the Active User

UX Theory card. Audit lens: Expectations.

Related cards in the deck: [Jakob's Law](jakobs-law.md), [Flow](flow.md).

## In one line

People do not read instructions. They start using the product straight away.

## What it asks of an interface

- People are motivated by the task in front of them. Reading documentation first feels like a detour.
- The paradox is that they would save time overall if they learned the system first. They still will not, so design for how people behave.
- Put guidance inside the product, at the moment and place it is needed: a hint beside the field, a tooltip on the control, an example in the empty state.
- Make help available whatever path people take, not only on a set tour.

## When it applies

- First-run experience, feature introductions, complex forms, empty states, error messages, anything that currently depends on a manual, tour or long instruction.

## Detect a violation

**In code**

- A blocking tutorial on first run: a multi-slide carousel, a full-screen overlay or a forced product tour before any real use. Look for onboarding modals triggered on first load with several steps.
- Instructions placed before the interface they describe: paragraphs above a form or tool. Their presence usually means the interface does not explain itself.
- Help that exists only outside the product: links to docs with no inline hint, example or tooltip at the point of need.
- Tours that cannot be skipped or reopened.
- Empty states with no example content, starting action or hint about what belongs there.
- Error messages that assume knowledge only the documentation gives.
- Features that work only if something was configured first, with nothing prompting the setup at the moment it is needed.

**In a screenshot or design file**

- Imagine all instructions were deleted. Could a newcomer still complete the main task?
- Count the words a person is expected to read before they can act.
- Overlays, coach marks and tours on first load.

## Example

**Bad:** A five-slide welcome carousel explaining features, followed by a blank workspace with no hint of what to do first.

**Good:** No carousel. The workspace opens with a sample project and one highlighted action, "Create your first board", and each tool shows a one-line tip the first time it is used.

## When laws conflict

- Against Discoverability (people need to learn what is possible): teach in context, one thing at a time, when it becomes relevant. Never up front in bulk.
- Against Flow: contextual help must not interrupt. Prefer inline hints and optional tooltips to modal coach marks.
- Against Hick's Law (progressive onboarding): introducing features gradually is right. Do it through the interface as people reach them, not through a tour.

## Origin

Described by John M. Carroll and Mary Beth Rosson in a 1987 chapter of Interfacing Thought: Cognitive Aspects of Human-Computer Interaction. Studying new users of office software, they found people skipped the manuals and started working at once, even when that led to errors and dead ends.

Cite as: John M. Carroll and Mary Beth Rosson, in Interfacing Thought (1987).
