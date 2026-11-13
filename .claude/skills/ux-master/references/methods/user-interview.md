# Workflow: user interview

A one-to-one conversation to learn what people are trying to do, how they do it now and
why. Use it to understand mental models before designing structure and naming, and to
explain what the numbers cannot (Campbell's Law).

## Plan

Ask for, or infer and confirm:

- **The learning goal:** one specific thing about behavior or attitude. "How freelancers
  decide when to send an invoice", not "learn about our users".
- **The decision it informs.**
- **Who to talk to:** which kind of user, and what makes someone a fit.
- **What is already known,** so the interview does not repeat it.

Produce a one-page plan:

```markdown
# Interview plan: <topic>

**Learning goal:** <one sentence>
**Decision this informs:** <what will change>
**Participants:** <who, how many, how recruited>
**Format:** <length, remote or in person, recorded or notes>
**Themes:** <3 to 5 areas to cover>
```

On numbers: there is no fixed rule. As a working heuristic, five to eight people from one
user group usually surface the main patterns, and you can stop when new interviews stop
adding new themes.

## Prepare

Write a discussion guide. It is a guide, not a questionnaire: themes with starter
questions and follow-ups.

1. **Opening:** thank them, explain the purpose, say there are no right answers, ask
   permission to record. Ask whether they have done an interview like this before, and
   reassure them it is just a conversation.
2. **Warm-up:** their role and a typical day or week. Easy to answer.
3. **Themes.** For each theme, two or three open questions about real past behavior:
   - "Tell me about the last time you ..."
   - "Walk me through how you ..."
   - "What happened next?"
   - "What was hard about that?"
   - "What did you do about it?"
4. **Follow-ups** to keep ready: "Why was that?" "Can you give me an example?" "What do
   you mean by ...?" Then silence. Let them fill it.
5. **Close:** "What should I have asked that I did not?" and whether you may follow up.

Check every question against these rules before you hand over the guide, and rewrite any
that fail:

| Rule | Instead of | Ask |
|---|---|---|
| Open, not yes or no | "Do you use reports?" | "How do you keep track of how the month went?" |
| Not leading | "How annoying is the export?" | "Tell me about the last time you exported something." |
| Past behavior, not prediction | "Would you use a mobile app?" | "When did you last need this away from your desk? What did you do?" |
| One thing at a time | "How do you invoice and chase payments?" | Two questions |
| Their words, not ours | "How do you use the Ledger module?" | "How do you record what you have been paid?" |
| No solutions | "Would a dashboard help?" | "What do you wish you knew at the start of each week?" |

## Run

People run the interviews. Advice for the interviewer: build rapport first, listen more
than you talk, follow the interesting thread even if it leaves the guide, and write down
exact words where you can.

## Synthesize

When the user brings back transcripts or notes:

1. **Extract observations.** One per note: something the person did, said, needed or
   struggled with. Keep the participant code and, for quotes, the exact words.
2. **Separate fact from interpretation.** "P3 keeps a spreadsheet beside the app" is an
   observation. "Users do not trust the app" is an interpretation: hold it for step 4.
3. **Group** the observations with the Affinity Mapping workflow.
4. **Write insights.** Each one states a pattern, the evidence for it (which
   participants) and what it means for the design.
5. **Capture vocabulary.** List the words participants used for the product's main
   objects and actions. These feed labels and navigation (Mental Model, Conceptual
   Model).

Output:

```markdown
# Interview findings: <topic>

**Interviews:** <n>, <who>, <dates>

## Insights
| # | Insight | Evidence | What it means for the design |
|---|---|---|---|
| 1 | <pattern> | P1, P4, P5: "<short quote>" | <action> |

## Their words
| Our term | What participants said |
|---|---|

## Surprises
- <anything that contradicted what the team believed>

## Still unknown
- <questions for the next round or another method>
```

## Pitfalls

- A goal so broad that every answer seems relevant.
- Asking people to predict their future behavior or design the solution.
- Pitching or explaining the product during the interview.
- Summarizing from memory instead of from notes.
- An agent writing "example answers". Do not.

## Connects to

Affinity Mapping for synthesis. User Personas and Journey Mapping as outputs. Jakob's Law
and Mental Model: interviews show which conventions and expectations your users bring.
