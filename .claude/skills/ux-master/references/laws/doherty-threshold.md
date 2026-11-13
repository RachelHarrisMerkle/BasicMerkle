# Doherty Threshold

UX Theory card. Audit lens: Signals and feedback.

Related cards in the deck: [Aesthetic-Usability Effect](aesthetic-usability-effect.md), [Flow](flow.md).

## In one line

People stay engaged and productive when the system responds within about 400 milliseconds, so that neither side is waiting on the other.

## What it asks of an interface

- Acknowledge every action within 400 ms. The work can take longer; the acknowledgment cannot.
- Perceived speed matters as much as real speed. Showing something useful early (the layout, a skeleton, the first results) shortens the wait people feel.
- Animation can hold attention during a short wait. Progress bars make longer waits tolerable, even when they are not exact.
- A short deliberate delay can make a result feel more considered and trustworthy when an instant answer would look fake. Use this rarely, and never before acknowledging the action.

## When it applies

- Every interaction with a server or a slow computation: submit, save, search, filter, upload, page transitions.
- Typing, dragging and scrolling, where delay is felt immediately.
- You cannot measure real response time from source or a screenshot. From those you can only check that feedback exists. Say so in a report, and measure on a running page if one is available.

## Detect a violation

**In code**

- Network or async calls with no immediate visual change: no pending state, disabled state, spinner, skeleton or optimistic update on the trigger or the affected region.
- Whole-page blocking loaders where part of the page could render first.
- Search, filter or validation that runs on every keystroke against a server with no local feedback, or that waits for a full round trip before showing anything.
- Animations and transitions on direct feedback longer than 400 ms: check `transition-duration`, `animation-duration` and spring settings on hover, press, open and close.
- Artificial delays (`setTimeout`, `sleep`, `delay`) before feedback. A deliberate delay on the result is acceptable only if input is acknowledged first.
- Long operations with an indeterminate spinner only. Jakob Nielsen's widely used response-time limits (about 0.1 second feels instant, about 1 second keeps the train of thought, about 10 seconds is the limit of attention) suggest showing progress and a way to cancel for anything near 10 seconds.
- Large unoptimized assets or render-blocking work on the first screen, when a running page is available to measure.

**In a screenshot or design file**

- No loading, skeleton or in-progress variant exists for a screen or component that depends on data.
- Buttons with no pressed or loading state in the design file.
- Long processes with no progress indicator or step count.

## Example

**Bad:** A search page that shows nothing for a second and a half after Enter, then replaces the whole page at once.

**Good:** Pressing Enter immediately shows the query in the heading and a skeleton list. Results fill in as they arrive, and a slow search shows "Still searching" with a cancel option.

## When laws conflict

- Against Peak-End Rule and Aesthetic-Usability Effect (long, pleasing transitions): speed wins for anything people do often. Keep feedback transitions short.
- Against the deck's own "purposeful delay" idea: acknowledgment is always immediate. Only the final result of a high-stakes process may be held back, and only if it helps trust. Never show progress that is not happening to keep someone waiting on a commercial message.
- With Feedback: Feedback says a response must exist. Doherty says how fast.

## Origin

In 1982 Walter J. Doherty and Ahrvind J. Thadani of IBM published research arguing that computer response time should be about 400 ms, not the 2 seconds that had been the accepted standard, because productivity rose sharply as response time fell.

Cite as: Walter J. Doherty and Ahrvind J. Thadani, IBM (1982).
