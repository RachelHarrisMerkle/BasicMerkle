# Zeigarnik Effect

UX Theory card. Audit lens: Progress and endings.

Related cards in the deck: [Goal-Gradient Effect](goal-gradient-effect.md), [Flow](flow.md).

## In one line

People remember unfinished or interrupted tasks better than finished ones.

## What it asks of an interface

- An open task stays on the mind. Showing that something is incomplete invites people to complete it.
- Signal clearly that there is more content to see, so people know to continue.
- Show progress toward a goal. A visible "not done yet" motivates more than no status at all.
- Credit real progress early so the task already feels started.
- The same pull turns into nagging if overused. Reserve it for tasks the person chose to begin.

## When it applies

- Onboarding checklists, profile and setup completion, drafts, saved carts, multi-session tasks, learning paths, long content with a clear end.
- Coming back after an interruption: the product should remember where the person was.

## Detect a violation

**In code**

- Multi-session tasks with no saved state: drafts not kept, a half-completed form reset on return, a cart emptied on logout.
- Incomplete items that look the same as complete ones in a list: no "Draft", "Incomplete" or "2 of 5" marker.
- No resume point: returning to a flow starts at step one instead of where the person stopped.
- Setup or onboarding with tasks remaining and nothing showing them: no checklist, count or progress.
- Content cut off with no cue that more exists (see Law of Closure and Signifiers).
- Overuse: permanent badges, repeated reminders or "complete your profile" banners for optional tasks, with no way to dismiss them.

**In a screenshot or design file**

- Any list of the person's own items: can you tell finished from unfinished at a glance?
- After setup: is there a visible account of what is still to do?
- Red badges or nags on things the person never started.

## Example

**Bad:** A course platform whose dashboard lists all courses identically, whether untouched, half done or complete, and reopens each at lesson one.

**Good:** Each course card shows "Lesson 4 of 9" with a progress bar and a "Resume" button that returns to the exact point.

## When laws conflict

- Against Cognitive Bias (honesty) and Selective Attention: use it for tasks the person started and benefits from finishing. A permanent incomplete badge on something optional is pressure, not help, and it trains people to ignore badges.
- Against Occam's Razor: a status marker on unfinished work is information, not decoration.
- With Goal-Gradient Effect: Zeigarnik brings people back to an open task; Goal-Gradient speeds them up as they near the end. Report them as one finding when both are missing from the same flow.

## Origin

Soviet psychologist Bluma Zeigarnik, working in Berlin with Kurt Lewin, published a study in 1927 in which participants recalled interrupted tasks better than ones they had completed. The effect has had mixed results in later replications, so use it as a design prompt, not a guarantee.

Cite as: Bluma Zeigarnik (1927).
