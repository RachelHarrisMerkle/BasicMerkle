# Workflow: UX survey

A set of questions sent to many users. Use it to learn how common something is, to get a
baseline before a change and a comparison after, or to find people for interviews and
tests. A survey measures what people say, so pair it with a method that observes what
they do (Campbell's Law).

## Plan

Ask for, or infer and confirm:

- **The question to answer,** and the decision it informs.
- **Who receives it** and how: in the product, by email, after a specific action.
- **What will be done with each answer.** If no decision depends on a question, cut it.

Produce a one-page plan:

```markdown
# Survey plan: <topic>

**Goal:** <what we need to learn>
**Decision this informs:** <what will change>
**Audience:** <who, how they are reached, when>
**Length:** <number of questions, expected minutes>
**Analysis:** <how each question will be used>
```

Keep it short. Completion drops as surveys get longer, so every question has to earn its
place (Principle of Least Effort applies to surveys too).

## Prepare

Write the survey, following the card's four points.

1. **Set expectations** in the introduction: what it is about, how long it takes, how
   answers are used, and who to contact with a problem.
2. **Ease in.** Start with broad, easy questions. Put demanding or sensitive ones later,
   and details about the respondent last.
3. **Write the questions.** Short, plain, one idea each. Mix closed questions (a fixed
   set of answers, easy to count) with a few open ones (free text, for the why).
4. **Remove bias.** Check every question against this table and rewrite any that fail.

| Problem | Example | Rewrite |
|---|---|---|
| Leading | "How helpful was our new dashboard?" | "How would you rate the dashboard?" with a balanced scale |
| Assumes a problem | "What problems did you have with export?" | "Describe your experience with export." |
| Double-barreled | "How easy and fast was checkout?" | Two questions |
| Unbalanced scale | Excellent, Very good, Good, Fair | The same number of positive and negative points, with a neutral middle |
| Jargon | "Rate the onboarding flow" | "Rate your first few minutes with the product" |
| Forced answer | No option fits | Add "Does not apply" or "Other" with a text field |
| Hypothetical | "Would you pay for X?" | Ask about past behavior, or test it another way |

5. **Use a standard measure when comparing over time.** The System Usability Scale (John
   Brooke, 1986) is a ten-statement questionnaire scored from 0 to 100. Use its standard
   wording and scoring exactly. A score near 68 is commonly cited as average (Jeff
   Sauro). Other single-question measures exist. Choose one and keep it the same between
   rounds.
6. **End** with an open "Anything else?" and, if wanted, an invitation to take part in an
   interview.

Output the survey as a numbered list with the answer type and options for each question,
plus the introduction and closing text. Recommend a pilot with two or three people to
catch confusing wording before it is sent.

## Run

People send the survey. The agent never fills in responses or estimates results.

## Synthesize

When the user brings back the responses:

1. **Report the basics first:** how many were invited, how many answered, and who they
   are. State whose views may be missing.
2. **Closed questions:** counts and percentages, with the number of answers beside every
   percentage. With small numbers, give counts only.
3. **Open questions:** treat each answer as a note and group them with the Affinity
   Mapping workflow. Report themes with how many answers support each and one or two
   exact quotes.
4. **Compare groups** only where each group is large enough to mean something. Say when
   it is not.
5. **Separate what the data shows from what you infer.**
6. **Recommend** actions, and name the follow-up method for anything the survey raised
   and could not explain.

Output:

```markdown
# Survey results: <topic>

**Responses:** <n> of <n invited> (<rate>), <dates>
**Who answered:** <summary, and who is under-represented>

## Headlines
1. <finding, with the number behind it>

## Results by question
| Question | Result | n |
|---|---|---|

## Themes from open answers
| Theme | Answers | Example quote |
|---|---|---|

## What we cannot conclude
- <limits of the sample or the questions>

## Recommended next steps
- <action or follow-up method>
```

## Pitfalls

- Asking what people would do instead of what they did.
- Reading opinions as behavior.
- Percentages from a handful of answers.
- A survey nobody decided what to do with.
- An agent generating responses "to preview the analysis". Use clearly labeled dummy
  rows only if the user asks for a template, and never report them as results.

## Connects to

Usability Test and Contextual Inquiry to observe what the survey can only ask about.
Affinity Mapping for the open answers.
