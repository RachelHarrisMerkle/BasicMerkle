# Workflow: journey mapping

A journey map lays out the steps a person goes through to reach a goal, with what they
do and how they feel at each step. Use it to see an experience end to end, find its worst
moments and its ending (Peak-End Rule), and decide what to fix first.

## Plan

Ask for, or infer and confirm:

- **Whose journey:** one persona or user type.
- **Which scenario:** one goal, with a clear start and end. "A new customer sends their
  first invoice", not "using the product".
- **What they expect** going in.
- **What evidence exists:** research notes, analytics, support conversations, or only
  the product itself.

Then choose a path and tell the user which you are on:

| Path | When | What you produce |
|---|---|---|
| Research-based map | Notes from interviews, tests or inquiry are provided | A map whose feelings and pain points cite their evidence |
| Assumption map | Only the product is available | A "Draft from assumptions" map: real steps, guessed feelings, a list to verify |

```markdown
# Journey map plan: <scenario>

**Lens:** <who, the scenario, their expectation>
**Scope:** <where the journey starts and ends>
**Evidence:** <sources, or "none yet: assumption map">
```

## Prepare

Gather the steps. If you have the product's code or screens, walk the flow and list every
step the person takes, including the ones outside the product: receiving an email,
finding a document, waiting. Steps are facts you can establish. Feelings are not.

Group the steps into three to six phases that the person would recognize, such as
Discover, Sign up, Set up, First use, Follow up.

The template follows the card's three sections: Lens, Experience, Insights.

```markdown
# Journey map: <scenario>

<!-- Assumption map only: -->
> Draft from assumptions. The steps are taken from the product. Feelings and pain points
> are predictions, not research. See "To verify" below.

## Lens
- **Who:** <persona or user type>
- **Scenario:** <what they are trying to do>
- **Expectation:** <what they expect, for example "done in ten minutes">

## Experience

| Phase | Step | What they do | Touchpoint | Thinking | Feeling (-2 to +2) | Evidence |
|---|---|---|---|---|---|---|
| Sign up | 1 | <action> | <screen, email, call> | <question in their mind> | +1 | P2, P4 |

**Emotional line:** <the feelings in order, for example +1, 0, -2, -1, +2>
**Lowest point:** step <n>, <why>
**Highest point:** step <n>, <why>
**The ending:** step <n>, <how it leaves them>

## Insights

| # | Pain point or opportunity | Step | Law | Owner | Metric |
|---|---|---|---|---|---|
| 1 | <what goes wrong, or what could be better> | 6 | <law or blank> | <team that owns it> | <how we would know it improved> |

## To verify
- <assumption> and <the method that would check it>
```

Rules for filling it in:

- **Feeling** uses a simple scale from -2 (frustrated) to +2 (delighted) so the line can
  be drawn. On a research-based map each rating cites its evidence. On an assumption map
  each rating is a prediction and the Evidence column says "assumed".
- **Thinking** holds the question in the person's mind at that step, in their words.
- **Insights** follow the card: each has the opportunity, who owns it inside the
  organization and the metric that would show it worked.
- **Law** is filled where a law explains the pain: a wait with no feedback is the Doherty
  Threshold, a step that asks for something entered earlier is Short-Term Memory, a bare
  ending is the Peak-End Rule.

## Run

No sessions are run for this method. If the map shows gaps in what is known, the
research happens in the interview, inquiry and usability test workflows.

## Synthesize

1. Complete the map.
2. **Find the peaks and the end.** Name the lowest point, the highest point and the final
   step. By the Peak-End Rule these three weigh most in what people remember. Fix the
   lowest point first.
3. **Check the expectation.** Compare the journey with what the person expected in the
   Lens. Where is it broken? Does the whole thing take longer than they thought
   (Parkinson's Law)?
4. **Rank the opportunities** by how many people reach that step and how bad the moment
   is.
5. **Hand off.** Interface problems can go to audit mode (`../modes/audit.md`) for the screens involved, or to
   fix mode as findings. Problems outside the interface go to their owner.

## Pitfalls

- Mapping the company's process instead of the person's experience.
- A scenario too broad to have a start and an end.
- Feelings invented and presented as findings.
- Opportunities with no owner and no metric.
- A map that ends at purchase or sign-up, missing what comes after.

## Connects to

User Personas supply the lens. User Interview and Contextual Inquiry supply the evidence.
Affinity Mapping groups pain points across several maps. Peak-End Rule and Cognitive
Bias are the cards behind why peaks and endings matter.
