# Workflow: design principles

Design principles are a short, agreed set of guidelines that say how a team approaches
design problems and how it decides when good options conflict. The deck suggests pairing
each principle with the UX theory behind it, so the principle carries its own reasoning.
This workflow does that.

## Plan

Ask for, or infer and confirm:

- **Who the principles are for** and what they should cover: the whole product, one
  area, content, interaction.
- **Who will take part.** The card's first step is to bring the team together, because
  principles nobody helped write are not adopted.
- **What already exists:** brand values, past decisions, research findings, recurring
  arguments in design reviews.
- **Format:** a live workshop the user runs, or a draft the agent prepares for the team
  to debate.

```markdown
# Design principles plan: <product or team>

**Scope:** <what the principles cover>
**Participants:** <who>
**Inputs:** <research, past decisions, known disagreements>
**Format:** <workshop of about 90 minutes, or a draft for review>
**Output:** <three to seven principles, each with its reasoning and examples>
```

Three to seven is a working heuristic: enough to cover the common conflicts and few
enough to remember.

## Prepare

### For a workshop

Write a facilitator's guide that follows the card's five steps.

1. **Rally the team** (5 minutes). State why principles are needed. Use a real recent
   disagreement as the example.
2. **Define the criteria** (10 minutes). On sticky notes, the group writes what a
   principle must be to be useful. Keep the result visible. Typical criteria: specific
   enough to settle an argument, focused on the user's needs, applicable across the
   product, and something a reasonable team could disagree with.
3. **Diverge** (10 minutes). Each person writes as many candidate principles as they can,
   one per note, without discussion.
4. **Converge** (30 minutes). Each person shares. Group the notes into themes as you go.
   Then everyone gets three votes for the themes that matter most.
5. **Refine and apply** (30 minutes). For the top themes, word a principle. Test each
   against real or hypothetical design work: does it change the decision? Merge
   overlaps and reword until each is clear. Agree how the principles will be shared and
   used.

Include prompts to get people writing: "What do we want users to say about using this?"
"What did we get wrong last time, and what rule would have prevented it?" "When speed
and clarity conflict, which do we choose?"

### For a draft

If the user wants a starting set, draft candidates from the inputs: past decisions that
show a pattern, research findings and recurring review comments. Mark the result "Draft
for the team to debate". Do not present it as the team's principles.

### The principle template

Each principle is written so that it can settle an argument.

```markdown
## <Principle, as a short instruction>

**What it means:** <one or two sentences, specific to this product>
**Why (the psychology):** <the law by name, and what it predicts>
**We choose this over:** <the good thing we are willing to give up>
**In practice:**
- Do: <a concrete example from this product>
- Do not: <a concrete example of the tempting alternative>
**How to check a design against it:** <a question a reviewer can answer yes or no>
```

Example:

```markdown
## Recommend, then let people choose

**What it means:** Wherever we ask people to pick, we show the option that suits most of
them first and keep the others one step away.
**Why (the psychology):** Hick's Law: decisions take longer as options multiply.
Supported by the Von Restorff Effect: the option that differs is the one people notice.
**We choose this over:** Showing everything we offer on one screen.
**In practice:**
- Do: three plans in view with one marked "Recommended", and a link to compare all.
- Do not: seven equal plans in a row.
**How to check a design against it:** At each choice, is one option clearly suggested,
and is it the right one for most users?
```

## Run

People run the workshop. If it is run as a draft, the user takes the draft to the team.

## Synthesize

When the user brings back the notes, votes and discussion:

1. **Cluster** the candidate notes with the Affinity Mapping workflow, if this was not
   done in the room.
2. **Write each chosen theme** in the principle template.
3. **Pair each with a law.** Use the card index in `../laws/INDEX.md` to find the card that
   explains why the principle works. If no law fits, say so and leave the line as plain
   reasoning. Not every principle needs a law.
4. **Test each principle** against these and fix or cut any that fail:
   - Could a reasonable team choose the opposite? If not ("be user-friendly"), it is a
     platitude.
   - Does it say what you give up?
   - Would it have changed a real past decision?
   - Can a reviewer check a design against it?
5. **Check the set.** Remove overlaps. Where two principles can conflict, say which wins,
   using the order in `../laws/which-law-wins.md`.
6. **Plan the use:** where the principles live, how they appear in design reviews and
   pull requests, and when they will be revisited. Justify mode (`../modes/justify.md`) can cite them.

Output the final set, a one-line version of each for quick reference, and the plan for
use.

## Pitfalls

- Platitudes nobody could disagree with.
- Principles written by one person, or by an agent, and announced.
- Too many to remember.
- No examples from the actual product.
- Principles that never appear in a review after the workshop.

## Connects to

Affinity Mapping to group the candidates. Every law card, as the reasoning behind a
principle. justify mode, which can cite a principle and its law in a rationale.
