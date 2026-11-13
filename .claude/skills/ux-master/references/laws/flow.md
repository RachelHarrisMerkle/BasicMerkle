# Flow

Psychology Concept card. Audit lens: Progress and endings.

Related cards in the deck: [Doherty Threshold](doherty-threshold.md), [Discoverability](discoverability.md).

## In one line

Flow is the state of being fully absorbed in an activity, with focused attention, a sense of control and enjoyment of the activity itself.

## What it asks of an interface

- Flow happens when the difficulty of the task is balanced with the person's skill. Too hard and people get frustrated; too easy and they get bored.
- An interface supports flow by responding quickly, giving clear feedback on every action and staying out of the way.
- Friction breaks flow: waits, interruptions, unexpected questions, having to hunt for the next control.
- Things people need next should be discoverable at the point they need them.

## When it applies

- Tools people work in for long stretches: editors, design tools, spreadsheets, inboxes, data entry, creative and learning products.
- Multi-step tasks where momentum matters.
- Less relevant to one-off transactional screens, where speed and clarity matter more than immersion.

## Detect a violation

**In code**

- Modal dialogs, confirmations or upsells that interrupt a routine, reversible action.
- Blocking spinners for operations that could run in the background or update optimistically.
- Focus that is lost or misplaced after an action: after adding an item, focus is not in the next input; after closing a dialog, focus does not return to the trigger.
- No keyboard path through a repeated task, or a path that needs the mouse at one step.
- Automatic interruptions during input: surveys, tooltips, chat prompts, session-expiry dialogs with no warning.
- Work lost on error, navigation or timeout because there is no autosave or draft.
- Difficulty that does not adapt: experts forced through beginner steps every time, or beginners dropped into an expert view.

**In a screenshot or design file**

- Walk the main repeated task. Count the points where the person must stop, wait, confirm or look elsewhere.
- Dialogs layered over a working surface for routine actions.
- No sign of saved state, so people have to stop and check.

## Example

**Bad:** A bulk tagging tool that opens a "Are you sure?" dialog for every tag applied and returns focus to the top of the list each time.

**Good:** Tags apply immediately with a brief "Tagged. Undo" notice, and focus moves to the next item so the whole list can be done from the keyboard.

## When laws conflict

- Against Feedback and Constraints (confirm, warn, validate): safety wins for irreversible actions; flow wins for reversible ones. Prefer undo to confirmation wherever undo is possible.
- Against Peak-End Rule (add a moment of delight): do not add celebration to a task people repeat many times a day.
- Against Paradox of the Active User: do not interrupt flow to teach. Offer help at the edge of the task, on request.

## Origin

Psychologist Mihaly Csikszentmihalyi named and described flow in the 1970s, most fully in Beyond Boredom and Anxiety (1975), from studies of people absorbed in activities such as climbing, chess and music.

Cite as: Mihaly Csikszentmihalyi, Beyond Boredom and Anxiety (1975).
