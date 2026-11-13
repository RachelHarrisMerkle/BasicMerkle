
# UX fix

Apply findings from a UX audit. The audit decided what is wrong. This mode changes the
code, deck or design file, one finding at a time, and proves each change worked.

## Rules

1. **Only what was approved.** Fix the findings the user named. "Fix all" means every
   finding in the report. Do not fix things the audit did not list. If you see a new
   problem, add it to "New findings" at the end and leave it alone.
2. **Smallest change that removes the evidence.** A finding is fixed when the evidence it
   cited is gone. Do not redesign around it.
3. **Use what the project already has.** Its components, tokens, spacing scale, naming
   and patterns. Add no library. Introduce a new style or component only when no existing
   one can express the fix, and say so.
4. **One finding at a time, edited in place.** Make targeted edits to the existing
   lines. Never rewrite or regenerate a whole file to apply several fixes at once: a
   rewrite hides what changed and can drop things nobody asked to change. Finish and
   re-check one finding before starting the next, so every change can be reviewed and
   reverted on its own.
5. **Do not break what works.** The audit's "What works" list is protected. Re-check it
   at the end.
6. **Decisions belong to the user.** If a fix needs a product or content decision, do not
   guess silently. See Step 2.

## Step 1: Load the findings

Find the audit report in the conversation or in the file the user points to. For each
approved finding note its number, severity, law, evidence and fix.

If there is no audit, do not invent one. Either run audit mode (`audit.md`) first, or, if the user
has named one specific problem, write it as a single finding row (law, evidence, fix)
and confirm it in one line before changing anything.

## Step 2: Plan the order

Size each fix:

| Size | Meaning | Examples |
|---|---|---|
| S | A value, attribute or label in one place | Padding on a button, an `autocomplete` value, a label's text, removing `checked` |
| M | Structure inside one component or section | Moving a button into its card, adding a pending state, grouping fields under headings |
| L | Flow, content or data | Removing plans, splitting a form into steps, adding a confirmation screen |

Order the work:

1. Smallest first: all S, then M, then L. Inside a size, most severe first.
2. Exception: if a larger fix will remove or replace the element a smaller fix touches,
   do the larger one first and drop the smaller one as "resolved by #n".
3. Mark any fix that needs a decision. Typical decisions: which option to recommend,
   which fields or plans to remove, what a message should say, what happens after
   success.

For each decision, ask one question with your recommended answer. If you cannot ask (you
are running unattended), apply the most conservative option, mark it "Assumed" in the
change log and say what to change if the assumption is wrong. Never remove content,
prices, legal text or fields on an assumption: restructure or flag instead.

## Step 3: Apply each fix

For every finding, in order:

1. **Re-read the evidence.** Open the cited lines. They may have moved after earlier
   fixes. Confirm the problem is still there.
2. **Change the least code that removes it,** with an edit to those lines. Match the
   surrounding code style.
3. **Re-check the finding.** Read the changed lines back, then run the same check that
   found it: recount the options, recompute the target size from width, height and
   padding, look for the state that was missing. The check must now pass. If you have a
   browser or test tool, confirm in the running page. Take the line numbers for your
   report from this read-back.
4. **Check the neighbors.** A fix can create a new problem: a bigger button that pushes
   another off the row, a new label that crowds a group, a new step that lengthens the
   task. If it does, settle it with the conflict order from `../laws/which-law-wins.md`: people can complete the task and are not misled,
   then they can predict what will happen, then effort is proportionate, then it
   motivates.

Fix patterns that are nearly always right:

- **Missing state:** add it in the component that owns the action, using the project's
  existing loading, error and success patterns.
- **Target too small:** grow the hit area with padding or `min-width` and `min-height`
  before changing the visible size.
- **Too many choices:** group, set a default or recommend one before removing anything.
- **Strict input:** normalize first (trim, strip spaces and punctuation, lowercase where
  safe), then validate the normalized value.
- **Grouping:** fix spacing first. Add a border or background only if spacing alone
  leaves it ambiguous.
- **Unclear control:** add a text label. Do not swap one icon for another.

## Step 4: Re-score

Look over the changed regions once more for anything the fixes introduced. Then recompute
the audit's score for the original scope. This is arithmetic, so always do it.

1. Start from the audit's full findings list.
2. Remove every finding that you fixed and that passed its re-check.
3. Keep every finding that was not approved, not fixed or only partly fixed. A partly
   fixed finding keeps its original severity. Lower it only if what remains is clearly
   less severe, and then say the new severity and the reason under "Not fixed". Add any
   new problem your changes introduced.
4. Score each lens from its worst remaining finding: 4 for none, 3 for P3, 2 for P2, 1
   for P1, 0 for any P0. Keep the audit's "n/a" lenses as they were.
5. Total = the sum, out of 4 times the number of lenses assessed.
6. Verdict: "Not ready" with any P0 still open or below 50%. "Needs work" with any P1 or from 50% to
   74%. "Solid" with no P0 or P1 and 75% to 89%. "Strong" with no P0 or P1 and 90% or
   more.

## Step 5: Report

Use this shape.

```markdown
# UX fixes applied: <what was fixed>

**Applied:** <n> of <n approved> · **Score:** <sum>/<max> (<percent>%) to <sum>/<max> (<percent>%) · **Verdict:** <before> to <after>

## Changes

| # | Sev | Law | What changed | Where | Re-check |
|---|-----|-----|--------------|-------|----------|
| 3 | P1 | Fitts' Law | `.close` hit area raised from 16x16 to 44x44 px with padding | `dialog.css:52` | Pass: 44x44, 8 px from nearest target |

## Assumed

- #<n>: <what you assumed, and what to change if it is wrong>

## Not fixed

- #<n>: <why: needs a decision, out of scope, or could not be verified>

## Still open from the audit

- #<n> (<severity>): <findings that were not in the approved set, one line each>

## New findings

- <anything you noticed while fixing that the audit did not list, with file:line>

## Check it

<one or two steps the user can take to see the result: the file to open, the action to try>
```

Leave out "Assumed", "Not fixed", "Still open from the audit" or "New findings" when they
are empty. Every row in "Changes" needs a location and a re-check result. "Pass" must say
what you measured or saw. If a re-check failed and you could not resolve it, the finding
goes under "Not fixed", not under "Changes".
