# Feedback

Interaction Principle card. Audit lens: Signals and feedback.

Related cards in the deck: [Mapping](mapping.md), [Usability Test](usability-test.md).

## In one line

After every action, the system shows that the action was received and what happened as a result.

## What it asks of an interface

- Feedback tells people the current state of the system. It keeps them in control and builds trust that the product works.
- Every action needs three answers: did it register, is it in progress, and did it succeed or fail.
- Feedback should be specific. "Saved" beats a generic check mark. "Card declined: check the expiry date" beats "Something went wrong".
- Progress indicators reassure people that work is happening. Use them truthfully.
- Silence is the failure. People repeat the action, or leave.

## When it applies

- Every button that changes data, submits, saves, deletes, sends, pays or navigates after a delay.
- Forms (validation), uploads, long-running jobs, toggles, drag and drop, copy to clipboard.
- State that persists: selected, active, current page, unsaved changes.

## Detect a violation

**In code**

- Async handlers (`fetch`, `await`, server actions, mutations, network calls) with no pending state: the trigger is not disabled, shows no spinner or label change, and nothing else on screen changes while the request runs.
- No error branch. `catch` blocks that are empty, only log, or set no user-visible state. Promises with no rejection handling.
- No success state: after a successful save or submit, nothing visible changes.
- Destructive or irreversible actions that complete with no confirmation of what was done and no undo.
- Missing interaction states in styles: no `:hover`, `:active`, `:focus-visible`, `[disabled]` or pressed style on interactive elements.
- Current location not indicated: navigation with no active or `aria-current` state.
- Form errors that say only "Invalid" or "Error", or appear far from the field they refer to.

**In a screenshot or design file**

- Buttons with only one visual state in the design file (no pressed, loading, disabled or focus variant).
- No loading, empty, error or success version of the screen exists anywhere in the file.
- Selected items, the active tab or the current step look the same as unselected ones.
- Error messages that do not say what went wrong or what to do next.

## Example

**Bad:** A "Create account" button that fires a request and stays unchanged for two seconds. If the email is taken, the form resets with a red "Error" line at the top of the page.

**Good:** On press the button switches to "Creating account..." and is disabled. On failure the email field keeps its value and shows "This email already has an account. Sign in instead?" beside it. On success the next screen confirms what was created.

## When laws conflict

- Against Flow and Principle of Least Effort (do not interrupt): feedback wins, but choose the quietest form that works. Inline state changes beat modal dialogs. For reversible actions, offer undo instead of asking for confirmation first.
- Against Occam's Razor (remove elements): states are not optional elements. A screen without its loading, error and success states is unfinished, not simple.
- With Doherty Threshold: feedback is what must arrive within 400 ms. The result can take longer.

## Origin

One of the fundamental principles of interaction described by Don Norman in The Design of Everyday Things. Norman treats immediate, informative feedback as a requirement for people to understand the result of their actions.

Cite as: Don Norman, The Design of Everyday Things (1988, revised 2013).
