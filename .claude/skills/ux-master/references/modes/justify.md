
# UX justify

Write the reasoning behind a design decision so that someone who was not in the room can
agree with it, challenge it or check it. Tie the decision to the psychology behind it,
which is what the Laws of UX deck is for.

A good rationale is short, names one law, points at evidence in the actual design, admits
the trade-off and says how to find out if it is wrong.

## Step 1: Pin down four things

Work them out from the conversation, the code or the audit. Ask only if you cannot tell.

- **The decision:** what was done or proposed, and where (a file and line, a screen, a
  finding number).
- **The alternative:** what someone wants instead, or what the obvious other option was.
- **The audience:** who has to be convinced. See "Audience" below.
- **The format:** a note, a pull request description, a one-liner or a pushback. Default
  to the note.

## Step 2: Choose the law

1. Pick the one law that carries the decision. Add at most one supporting law. More than
   two reads as a list, not a reason.
2. Open [origins.md](origins.md) and find that law. Use its
   one-line statement and its citation line.
3. If the alternative is backed by another law, name it. Then say why this one wins,
   using the order of concerns: people can complete the task and are not misled, then
   they can predict what will happen, then effort is proportionate, then it motivates.
   The full table is in `../laws/which-law-wins.md`.

## Step 3: Write it

### Format A: stakeholder note (default)

About 100 to 150 words. Use these five labels.

```markdown
**Decision:** <what we did, as the user experiences it>
**Why:** <the law by name, in one plain sentence, and what it predicts here>
**Evidence in this design:** <what in the design shows it: a count, a size, a line, a finding>
**Trade-off:** <what this costs or what we gave up, and why it is still the right call>
**How we will know:** <one thing to measure and one thing to watch, with the method>

Source: <citation line from origins.md>
```

Example:

```markdown
**Decision:** The pricing page shows three plans with one marked "Recommended", and the
other four plans sit behind "Compare all plans".
**Why:** Hick's Law: the time it takes to decide grows with the number and complexity of
options. Seven equal plans made the first decision on the page the hardest one.
**Evidence in this design:** The previous page had seven cards with identical styling and
feature lists in seven different orders (`pricing.html:92-187`).
**Trade-off:** Four plans are one click further away. People who need them are looking
for a specific tier and will follow a clearly labeled link.
**How we will know:** Plan-selection rate on the page, checked against a five-person
usability test to confirm people can still find the larger plans.

Source: William Edmund Hick (1952) and Ray Hyman (1953).
```

### Format B: pull request description

```markdown
## What changed
<one or two lines, user-facing>

## Why (UX)
- <Law>: <one sentence tying the change to the law> (<file:line or screen>)

## Trade-offs
- <what it costs>

## How to verify
- [ ] <a check a reviewer can do in the running interface>
```

### Format C: one-liner

For a design review comment, a code comment or a commit body. One sentence: the decision,
"because", the law, the consequence for the user.

`Recommended plan is visually distinct because of the Von Restorff Effect: in a row of similar cards, the one that differs is the one people notice and remember.`

### Format D: pushback

When someone has asked for a change that would hurt usability. Be useful to them: they
have a goal, and the answer is another way to reach it.

```markdown
**The request:** <what was asked, stated fairly>
**The goal behind it:** <what they are trying to achieve>
**The risk:** <the law, and what it predicts will happen to users>
**Another way to reach the goal:** <a concrete alternative that serves the same goal>
**If we go ahead anyway:** <the least harmful version, and what to watch>
```

## Audience

| Audience | Lead with | Leave out |
|---|---|---|
| Executive or client | The outcome and the risk to their customers, in their words | Jargon, the mechanics of the law |
| Product manager | The trade-off and how it will be measured | Visual detail |
| Engineer | The constraint as a number or a testable rule, and where it lives in the code | Persuasion |
| Designer | The law, the conflict it won and the alternative considered | Basics |

Name the law for every audience. The name gives people a shared word for the idea and
something they can look up.

## Honesty rules

These keep the rationale credible. One overstated claim loses the argument.

- **Laws describe tendencies.** Write "tends to", "is likely to", "predicts". Never
  promise a conversion rate, a percentage lift or a guaranteed result.
- **No invented evidence.** Use only the facts and citation lines in `origins.md`. Do not
  add studies, sample sizes or statistics from memory.
- **Keep the caveat.** Some laws are often overstated. If you cite one of these, keep its
  limit in the sentence:
  - Miller's Law is about memory, not about how many items may appear on a screen.
  - Hick's Law is about simple choices and gives no maximum number of options.
  - Choice overload (Analysis Paralysis) is real but depends on context.
  - Zeigarnik Effect has mixed support in later replications.
- **Say what kind of claim it is.** A law of psychology, a published standard (WCAG,
  Apple or Google guidance) and a convention (Jakob's Law) are three different kinds of
  backing. Name the right one.
- **Evidence from this design, not in general.** Point at the count, size, line or
  finding. If you have none, say the rationale is a hypothesis.
- **Admit a guess.** If the decision is a judgment call that the laws do not settle,
  say so and name the method that would test it. Research mode (`research.md`) can plan it.
- **A number is not proof on its own.** When you propose a metric, pair it with something
  observed (Campbell's Law).
