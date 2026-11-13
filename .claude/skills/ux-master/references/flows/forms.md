# Playbook: forms

Sign-up, log-in, contact, settings, data entry and any other screen where people type.

## Laws that matter most

1. **Principle of Least Effort.** Every field is a cost. People leave forms that ask for
   more than the task seems to need.
2. **Postel's Law.** People type things in many formats. The form should cope.
3. **Feedback.** People need to know what went wrong, where, and how to fix it, without
   losing what they typed.
4. **Chunking and Law of Proximity.** Grouping and spacing turn a wall of fields into a
   few parts.
5. **Tesler's Law and Parkinson's Law.** Let the system do the work (autofill, defaults,
   inference) so the task takes less time than people expect.
6. **Fitts' Law.** Controls and labels must be easy to hit, and the submit button must
   sit where the form ends.

## Build rules

1. **Ask only what this step needs.** For each field, name what breaks if it is removed
   or asked later. If nothing breaks, remove it or defer it.
2. **Mark the minority.** If most fields are required, mark the optional ones "optional".
   If most are optional, mark the required ones.
3. **One column.** Stack fields on one left edge (Law of Continuity). Put fields side by
   side only when they are read as one unit, such as city, state and postal code.
4. **A visible label above every field.** Never use the placeholder as the label. Use the
   placeholder for an example at most.
5. **Group and space.** Put related fields under a short heading. Use clearly less space
   between a label and its field than between one field and the next label, and more
   again before a new group.
6. **Right input for the data.** Email, telephone, number, URL, date and password inputs,
   or the native equivalents, with the matching keyboard. Use a select, radio group or
   picker when the valid set is known (Constraints).
7. **Help the browser help the user.** Set `autocomplete` (or the platform's content
   type) on name, email, telephone, address, card and one-time-code fields. Never block
   paste.
8. **Accept, normalize, then validate.** Trim whitespace. Allow spaces, dashes and
   brackets in phone and card numbers. Lowercase the domain of an email. Do not restrict
   names with patterns or short maximum lengths.
9. **Show rules before they are broken.** Put password rules and format hints beside the
   field from the start (Short-Term Memory).
10. **Validate when the person leaves a field, and again on submit.** Not on every
    keystroke while they are still typing.
11. **Put the error next to the field.** Say what is wrong and how to fix it in plain
    words. Keep everything the person typed. Move focus to the first error and announce
    it to assistive technology.
12. **One primary button, at the end of the form, on the same edge as the fields.** Its
    label says what happens ("Create account", not "Submit"). A destructive or reset
    action, if it must exist, looks different and sits apart (Stroop Effect).
13. **Acknowledge submit within 400 ms** (Doherty Threshold). Disable the button and
    show a pending label, then show success or the error.
14. **Offer a show-password toggle instead of a confirm-password field.** Do not ask for
    the email twice.
15. **Save progress on long forms** and say that it is saved (Zeigarnik Effect).

## Checks

| Check | Law |
|---|---|
| Count the inputs. Can each one name a reason to be asked now? | Principle of Least Effort |
| Every input has a persistent visible label, linked to it in code. | Signifiers, Fitts' Law |
| Optional or required is marked. | Signifiers |
| Input types and `autocomplete` values are set; paste works. | Tesler's Law, Parkinson's Law |
| Validation accepts spaces in phone and card numbers, any letter case in email, and names with apostrophes, hyphens and non-Latin letters. | Postel's Law |
| Values from a known set use a constrained control. | Constraints |
| Label-to-field spacing is clearly smaller than field-to-field spacing. | Law of Proximity |
| Fields share one left edge; tab order matches visual order. | Law of Continuity |
| Errors appear beside the field, say how to fix it, and input is kept. | Feedback |
| Format and password rules are visible before the first attempt. | Short-Term Memory |
| The submit action shows a pending state at once and a result after. | Doherty Threshold, Feedback |
| Controls meet the target minimum for the platform: 24 by 24 CSS px for WCAG 2.2 AA on the web, 44 by 44 pt on Apple platforms, 48 by 48 dp on Android. Checkboxes and radio buttons count: the label must be part of the target. | Fitts' Law |
| Submit and any reset, cancel or delete action look different and do not touch. | Stroop Effect |
| The end of the form confirms what happened and what comes next. | Peak-End Rule |

## Mistakes this screen invites

The wall of fields, the placeholder label, the strict input, the silent button, the
blame-y error, the twin buttons, the uniform gap, the reinvented control, the dead end.

## When laws conflict here

- **Fewer fields against complete data.** The business wants more data, the person wants
  to finish. Ask for the minimum now and the rest later, in context, when the reason is
  obvious (Principle of Least Effort over Pareto-style "nice to have").
- **One page against steps.** One page with headed groups for a single decision. Separate
  steps when the form holds separate decisions or runs past a couple of screens, and then
  show progress (Goal-Gradient Effect).
- **Constraints against Postel's Law.** Constrain choices with pickers. Be liberal with
  typed formats.
- **Inline validation against Flow.** Do not interrupt typing. Validate on leaving the
  field.

## Research that settles what the laws cannot

Which fields people think are reasonable, and what they call things: a usability test of
the form with five or so people, and a look at where real submissions fail.
