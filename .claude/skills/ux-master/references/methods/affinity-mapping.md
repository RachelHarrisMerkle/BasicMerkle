# Workflow: affinity mapping

Sort qualitative notes into groups to find themes, then turn the themes into insights and
actions. This is the synthesis step for interviews, usability tests, contextual
inquiries and open survey answers. It is also the method where an agent helps most,
because clustering many notes is slow by hand.

## Plan

Ask for, or infer and confirm:

- **The material:** transcripts, session notes, survey answers, support tickets, audit
  findings from several screens.
- **The question the synthesis should answer.**
- **Who needs to agree with the result.** If a team does, plan to review the draft
  clusters together instead of presenting them as finished.

No participants are recruited for this method. The plan is short:

```markdown
# Affinity mapping plan: <topic>

**Sources:** <what material, from how many sessions or respondents>
**Question:** <what we want the themes to tell us>
**Review:** <who will check and challenge the clusters>
```

## Prepare

Turn the material into notes. This is the card's first step, Record.

1. **One observation per note.** A thing someone did, said, needed or struggled with. A
   long answer becomes several notes.
2. **Keep the source on every note:** a participant code and the session, such as
   `P3, interview`. Never drop it.
3. **Keep the person's words** for quotes. Do not tidy them into your own phrasing.
4. **Mark the kind of note:** observation, quote, or the researcher's interpretation.
   Cluster observations and quotes. Hold interpretations aside.
5. **Remove personal details** that are not needed.

Output a numbered note list:

| # | Note | Kind | Source |
|---|---|---|---|
| 1 | Keeps a paper list of client codes beside the keyboard | Observation | P2, inquiry |

Ask the user to check the list before you cluster, if the material was messy. You must
not add notes that are not in the material.

## Run

Follow the card's steps Identify and Label.

1. **Cluster from the bottom up.** Put notes together because they are about the same
   thing, not into categories decided in advance. Do not start from the laws, the
   product's features or the interview questions.
2. **Move quickly, then revise.** Groups can change. Split a group that holds two ideas.
   Merge groups that say the same thing.
3. **Let singles stand.** A note that fits nowhere stays on its own. Do not force it.
4. **Name each cluster as a finding,** a sentence that says what was seen: "People
   re-enter the same client details for every invoice", not "Data entry".
5. **Group the clusters** into a few higher themes if there are many.
6. **Count the spread:** how many notes and how many different participants are behind
   each cluster. One talkative participant is not a pattern.

Present the clusters as a draft and invite the user to move notes. Say where you were
unsure.

## Synthesize

The card's last step, Insights.

1. **Write an insight for each strong cluster:** the pattern, why it matters and what it
   means for the design.
2. **Give the evidence:** participant codes and one or two exact quotes.
3. **Tag a law** where one explains the pattern. Leave it blank where none does.
4. **Attach a design action** to every insight. The card is explicit about this: themes
   without actions are not finished.
5. **Rank** by how many participants were affected and how much it cost them.
6. **Tell the story.** Two or three sentences on what the themes say together.

Output:

```markdown
# Affinity map: <topic>

**Sources:** <n notes from n participants or sessions>

## The story
<two or three sentences>

## Themes and insights
| # | Theme (as a finding) | Notes | Participants | Insight | Law | Design action |
|---|---|---|---|---|---|---|
| 1 | <sentence> | 9 | P1, P2, P4, P6 | <what it means> | <law or blank> | <action> |

## Evidence
### Theme 1: <name>
- "<exact quote>" (P2)
- <observation> (P4)

## Outliers worth keeping
- <single notes that may matter>

## What this does not tell us
- <gaps, and the method that would fill them>
```

## Pitfalls

- Sorting into ready-made categories, which only confirms what you already thought.
- Cluster names that are topics instead of findings.
- Counting notes instead of people.
- Losing the link from a theme back to its notes.
- Adding plausible notes to fill out a thin cluster. Never.

## Connects to

Every research method in this folder feeds it. Its themes become User Personas, Journey
Mapping and Design Principles. Actions that change the interface can go to fix mode (`../modes/fix.md`).
