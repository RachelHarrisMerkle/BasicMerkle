# Workflow: usability test

Watch representative users try realistic tasks with the design. It finds the problems an
inspection cannot, and it is the check for a design that looks good and may not work
(Aesthetic-Usability Effect).

## Plan

Ask for, or infer and confirm:

- **What is being tested:** a live product, a prototype or a competitor. Which screens.
- **The decision it informs:** what will change depending on the result.
- **Who the users are:** the people the product is for. Not the team, unless the product
  is for the team.
- **What "success" means** for each task.

Produce a one-page plan:

```markdown
# Usability test plan: <product or feature>

**Goal:** <the question this test answers>
**What we will test:** <build or prototype, and the screens in scope>
**Participants:** <who, how many, how recruited, what excludes someone>
**Format:** <moderated or unmoderated, in person or remote, session length>
**Tasks:** <3 to 6, listed below>
**Measures:** <completion, time on task, errors, a confidence or ease rating>
**Roles:** <moderator, note-taker>
**Schedule:** <dates>
```

On numbers: Jakob Nielsen's long-standing guidance for qualitative testing is about five
participants per round, with several small rounds between design changes instead of one
large one. Treat it as guidance, not a rule. Test with more when user groups differ a
lot.

## Prepare

Write the session script.

1. **Introduction** (read aloud): who you are, that the design is being tested and not
   the person, that there are no wrong answers, that you did not design it so they can be
   frank, a request to think aloud, and consent to record.
2. **Warm-up questions:** two or three about their context and how they do this today.
3. **Tasks.** Write each as a scenario with a goal, in the user's words, without using
   the labels on the screen. Good: "You want your team to get a copy of every invoice.
   Set that up." Bad: "Click Settings and turn on Invoice CC."
   - Order tasks from simple to hard, and start with one most people will complete.
   - Give each task a success criterion and a time after which you move on.
   - Take tasks from the product's main jobs and from any audit findings you want to
     confirm.
4. **Neutral prompts** for when someone goes quiet or gets stuck: "What are you thinking?"
   "What would you expect to happen?" "What would you do if I were not here?" Do not
   explain, hint or defend the design.
5. **After each task:** "How easy or hard was that, from 1 to 5?" and "Why?"
6. **Wrap-up:** what stood out, what they would change, anything missing.

Also produce an observation sheet, one per participant:

| Task | Completed (yes, with help, no) | Time | Errors and wrong turns | Quotes | Rating 1 to 5 |
|---|---|---|---|---|---|

## Run

People run the sessions. Remind the moderator of the card's four points: recruit real
users, simulate real tasks, observe and stay neutral, and measure performance as well as
opinion. What people say about a task and how they performed on it often differ, so
record both.

## Synthesize

When the user brings back notes, recordings summaries or filled sheets:

1. **Tabulate** completion, time and rating per task across participants.
2. **List every observed problem** once, with the participants who hit it (P1, P3, P4).
3. **Rate each problem** with the audit severity scale: P0 the task could not be
   completed, P1 many struggled or erred, P2 friction most got past, P3 minor.
4. **Tag a law** where one explains the problem. Leave it blank where none does.
5. **Note the gaps between saying and doing:** tasks rated easy that people failed, or
   the reverse.
6. **Recommend a fix** for each problem, most severe first.

Output:

```markdown
# Usability test findings: <product or feature>

**Sessions:** <n> participants, <dates>, <format>

## Task results
| Task | Completed | With help | Failed | Median time | Median rating |
|---|---|---|---|---|---|

## Problems found
| # | Sev | What happened | Who | Law | Recommended fix |
|---|---|---|---|---|---|

## What worked
- <things people did easily; keep these>

## Said one thing, did another
- <where ratings and performance disagreed>

## Open questions
- <what this test could not answer, and the method that would>
```

## Pitfalls

- Testing with colleagues or friends who already know the product.
- Tasks that give away the answer by using the interface's own words.
- Helping participants when they struggle. The struggle is the data.
- Reporting opinions ("they liked it") instead of behavior.
- Calling an agent's walkthrough a usability test.

## Connects to

Affinity Mapping to group findings across sessions. Jakob's Law, when problems come from
broken conventions. the fix mode (`../modes/fix.md`) to apply interface changes.
