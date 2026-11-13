# Workflow: user personas

A persona is a fictional profile that stands for a real group of users, built from
research. It gives a team one shared answer to "who is this for?" and helps judge which
conventions and expectations users bring (Jakob's Law, Mental Model).

## Plan

Ask for, or infer and confirm:

- **What the personas will be used for:** prioritizing features, writing test tasks,
  onboarding new team members.
- **What evidence exists:** interview notes, usability findings, survey results, support
  conversations, analytics.
- **How many user groups** the team believes there are. Research may change the answer.

Then choose one of two paths, and tell the user which you are on:

| Path | When | What you produce |
|---|---|---|
| Research-based persona | Real notes or data are provided | A persona whose every trait cites its evidence |
| Proto-persona | No research yet | A "Draft from assumptions" persona, with a list of what to verify |

```markdown
# Persona plan: <product>

**Purpose:** <the decisions these personas will inform>
**Evidence:** <sources, or "none yet: proto-personas">
**Groups expected:** <how many, and what separates them>
```

## Prepare

Personas are separated by behavior and goals, not by demographics. Two people of the same
age and job who use the product in different ways are two personas. Two people of
different ages who use it the same way are one.

1. From the evidence, list the behaviors and goals that differ between users: how often
   they use the product, what they use it for, how expert they are, what they do when
   stuck, who else is involved.
2. Find the people who cluster together on those. Each cluster is a candidate persona.
3. Keep the set small. A few distinct personas the team will remember are more useful
   than many it will not.

The template follows the card's three sections.

```markdown
# <Name>, "<a short tagline that captures them>"

<!-- Proto-persona only: -->
> Draft from assumptions. Not yet based on research. See "To verify" below.

## Info
- **Role or situation:** <occupation or context>
- **Basics:** <only details that affect design, such as age range or location>
- **Image:** <a note describing a suitable photo or sketch>

## Details
**Bio.** <three or four sentences: who they are in relation to this product>

**Goals**
- <what they are trying to achieve> [P2, P5]

**Motivations**
- <why it matters to them> [P1]

**Behaviors**
- <what they actually do: tools, frequency, habits> [P2, P3, P5]

**Frustrations**
- <what gets in their way> [P3, P5]

**Tasks with the product**
- <the main things they would do>

## Insights
**Attitude.** <how they feel about this kind of product or task>

**In their words**
- "<exact quote from research>" (P5)

**What they already know.** <products and conventions they are used to>

## Design implications
- <what this persona means for the interface, with the law where one applies>

## To verify
- <assumption> and <the method that would check it>
```

Rules for filling it in:

- **Research-based:** every goal, behavior and frustration carries the participant codes
  it came from. Quotes are exact. If a section has no evidence, write "No evidence yet"
  instead of filling it.
- **Proto-persona:** keep the warning line. Leave "In their words" empty. Never write a
  quote nobody said. List every assumption under "To verify".
- Give the persona a realistic name and a tagline so the team can refer to them. Do not
  add personality details for color. Invented hobbies and brand preferences make a
  persona feel real without making it true.

## Run

No sessions are run for this method. The research happens in the interview, inquiry,
survey and usability test workflows.

## Synthesize

1. Write the personas from the template.
2. Add a one-table summary for quick reference:

| Persona | Main goal | Uses the product | Biggest frustration | Design priority |
|---|---|---|---|---|

3. Name the primary persona: the one whose needs must be met for the product to work.
   Say why.
4. For proto-personas, finish with the shortest research plan that would validate them.
   Usually this is a handful of interviews with the User Interview workflow.

## Pitfalls

- Personas built from demographics, with behavior added afterward.
- Invented quotes and invented detail.
- So many personas that none guides a decision.
- Personas made once and never used. Tie each to a decision.
- Treating a proto-persona as research. It is a hypothesis.

## Connects to

User Interview and Contextual Inquiry supply the evidence. Journey Mapping uses a persona
as its lens. Usability Test recruits against the persona's defining behaviors.
