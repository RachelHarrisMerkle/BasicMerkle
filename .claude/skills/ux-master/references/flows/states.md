# Playbook: empty, loading, error and success states

Every screen that shows data or takes an action has more than one state. The happy path
is the one that gets built. The others are where trust is won or lost.

## Laws that matter most

1. **Feedback.** After every action, and whenever data is on its way, the interface says
   what is happening and what happened.
2. **Doherty Threshold.** The acknowledgment arrives within 400 ms, even when the result
   takes longer.
3. **Peak-End Rule.** Errors are the low points and confirmations are the endings. Both
   weigh heavily in what people remember.
4. **Paradox of the Active User.** An empty screen is where a new user decides what to do
   next. Instructions elsewhere will not be read.
5. **Postel's Law.** Things go wrong: bad input, no network, no results. The interface
   should expect it.
6. **Selective Attention.** A message that appears away from where the person is looking
   will be missed.

## The states to cover

For each screen and each component that depends on data or performs an action, decide
which of these exist and build them.

| State | The person should learn |
|---|---|
| Empty, first use | What belongs here and how to add the first one |
| Empty, no results | That the search or filter returned nothing, and how to widen it |
| Empty, cleared | That everything is done (an inbox at zero) |
| Loading | That something is coming, and roughly what |
| Partial | Which parts are ready and which are still loading or failed |
| Error | What went wrong, whether their work is safe, and what to do next |
| Offline or degraded | What still works and what will sync later |
| Success | What happened and what comes next |
| Disabled | Why the control is unavailable and how to make it available |
| In progress | That their action was received and is being carried out |

## Build rules

1. **Acknowledge within 400 ms.** A pressed style, a label change, a spinner on the
   control or an optimistic update. Then show the result when it is ready.
2. **Match the indicator to the wait.** Under about a second: a state change on the
   control is enough. A few seconds: a skeleton shaped like the content, or a spinner
   with a label. Around ten seconds or more: progress, what is happening, and a way to
   cancel or carry on with something else.
3. **Load in place.** Keep the layout stable. Placeholders take the shape and size of the
   content, so nothing jumps when it arrives. Prefer loading a region to blocking the
   whole page.
4. **Keep the previous content while refreshing** and mark it as updating, instead of
   clearing the screen.
5. **Give empty first-use states a job.** One sentence on what goes here, one primary
   action to add the first item, and sample content or an example where it helps.
6. **Make "no results" different from "nothing yet".** Repeat the query or filters, and
   offer to clear them.
7. **Write errors as help.** Say what happened in plain words, say whether the person's
   work is safe, and give the next step: retry, edit, another route, or who to contact.
   No codes or stack traces as the message. No blame.
8. **Put the message where the problem is.** Field errors beside the field. Action errors
   near the control that was pressed. Page-level errors in the content area, in the
   layout, not as a banner that looks like a promotion.
9. **Never lose work on an error.** Keep form input, keep the draft, keep the selection.
10. **Make errors recoverable.** Offer a retry that works. Prefer undo to confirmation
    for reversible actions.
11. **Confirm success specifically.** Say what was done, in the past tense, using the
    same verb as the button ("Publish" then "Published"). For significant actions add
    the details and the next step. For routine ones a brief inline confirmation is
    enough.
12. **Do not rely on a vanishing toast for anything important.** If the person needs the
    information, it stays on screen or can be found again.
13. **Explain disabled controls.** Say why the control is unavailable, in text nearby or
    on focus and hover. Do not disable a submit button with no clue about what is
    missing.
14. **Use more than color** for error, warning and success: an icon and words as well.
15. **Announce changes** to assistive technology (a live region or the platform's
    equivalent), and move focus to the message when the person has to act on it.

## Checks

| Check | Law |
|---|---|
| For every action that calls a server: is there a pending state on or near the control? | Feedback, Doherty Threshold |
| For every data region: is there a loading state shaped like the content? | Doherty Threshold, Law of Closure |
| For every list, table or feed: is there a first-use empty state with one action, and a separate no-results state? | Paradox of the Active User, Feedback |
| For every request: is there an error state that says what happened and what to do? | Feedback |
| Is user input kept after an error? | Peak-End Rule, Postel's Law |
| Do errors appear next to their cause? | Selective Attention, Simon Effect |
| Is there a retry or another way forward from every error? | Peak-End Rule |
| Does each significant action end with a confirmation that names what happened and the next step? | Peak-End Rule |
| Do long operations show progress and a way to cancel? | Doherty Threshold, Goal-Gradient Effect |
| Are disabled controls explained? | Signifiers, Constraints |
| Are states signaled by more than color? | Von Restorff Effect |
| Do important messages persist, instead of disappearing on a timer? | Selective Attention, Short-Term Memory |
| Does the layout stay stable when content loads? | Aesthetic-Usability Effect |

## Mistakes this screen invites

The silent button, the dead end, the blame-y error, the color-only signal, the welcome
tour used in place of a useful empty state.

## When laws conflict here

- **Feedback against Flow.** Choose the quietest signal that works. Inline state changes
  for routine actions, a dialog only when the person must decide something.
- **Confirmation against speed.** Undo for reversible actions. Confirm only what cannot
  be undone and is costly.
- **Celebration against speed.** A designed success moment suits rare milestones, not
  actions people repeat all day.
- **Fewer elements against states.** States are part of the screen. A screen without
  them is unfinished, not minimal.
- **A quick result against a deliberate delay.** Acknowledge at once. A short held-back
  result is acceptable only where an instant answer would look untrustworthy, and never
  to make room for a sales message.

## Research that settles what the laws cannot

Which errors people hit in practice, and whether they understand the messages: read support
conversations and error logs, then run a usability test in which you trigger the common
failures on purpose.
