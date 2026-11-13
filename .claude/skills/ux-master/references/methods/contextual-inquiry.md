# Workflow: contextual inquiry

Observe a small number of users doing their real work in the place where they do it, and
ask about what you see. Use it when the product supports real work with interruptions,
other tools and workarounds that no analytics shows.

## Plan

Ask for, or infer and confirm:

- **The work to observe:** which activity, from where to where.
- **Why observation and not an interview:** what people may be unable to describe.
- **Who and where:** which users, in which setting, and what access is needed.
- **Constraints:** confidentiality, what may be photographed or recorded.

Produce a one-page plan:

```markdown
# Contextual inquiry plan: <activity>

**Focus:** <the work we want to understand>
**Decision this informs:** <what will change>
**Participants and setting:** <who, where, how many sessions, how long>
**What we will capture:** <notes, photos of the workspace, artifacts, recordings if permitted>
**Permissions needed:** <from the participant and their organization>
```

A handful of sessions is typical, because each one is long and rich. This is a working
heuristic, not a rule.

## Prepare

Write a field guide for the observer.

1. **Introduction:** who you are, the goal, what will happen, and that what they share is
   confidential.
2. **Setting the frame:** "I would like to watch you work as you normally do. I will ask
   questions now and then when I see something I want to understand. You are the expert
   and I am here to learn."
3. **Things to watch for:**
   - The sequence of steps and where it differs from the official process.
   - Tools used alongside the product: spreadsheets, paper notes, other apps.
   - Workarounds, repeated actions and anything copied from one place to another.
   - Interruptions, waits and switches of attention.
   - What they have to remember or look up (Short-Term Memory).
   - Points of hesitation, frustration or satisfaction.
4. **Questions to ask in the moment:** "What are you doing now?" "Why that way?" "What
   are you looking for?" "Is this how it usually goes?" "What would have happened if ...?"
5. **Wrap-up:** play back your understanding of the process and ask them to correct it.
   Ask what you did not see today that happens at other times.

Also produce a note template:

| Time | What they did | Tool or screen | What they said | My question or interpretation |
|---|---|---|---|---|

Keep observation and interpretation in separate columns.

## Run

People run the sessions. The card's five steps: introduce, inform, explore, clarify,
synthesize. Advice for the observer: watch more than you ask, do not correct or teach,
and collect copies of the artifacts people create for themselves.

## Synthesize

When the user brings back field notes:

1. **Reconstruct the real workflow** for each participant as a numbered sequence, with
   the tools used at each step.
2. **Compare across participants.** Mark steps everyone does, steps that vary and steps
   the official process does not include.
3. **List breakdowns:** workarounds, re-entry of data, waits, errors, things remembered
   or written down to carry between tools.
4. **Group** the observations with the Affinity Mapping workflow.
5. **Tag a law** where one explains a breakdown: copying a value between screens is
   Short-Term Memory, a workaround for a rigid field is Postel's Law, doing by hand what
   the system could do is Tesler's Law.
6. **Turn breakdowns into opportunities,** most frequent and most costly first.

Output:

```markdown
# Contextual inquiry findings: <activity>

**Sessions:** <n>, <who>, <where>, <dates>

## How the work is really done
1. <step> (<tool>)

## Breakdowns and workarounds
| # | What we saw | Who | Cost to the person | Law | Opportunity |
|---|---|---|---|---|---|

## Environment
- <what in the setting shapes use: devices, noise, interruptions, shared screens>

## Artifacts collected
- <cheat sheets, spreadsheets, notes, and what each one compensates for>

## Still unknown
- <what to observe next>
```

## Pitfalls

- Turning it into a sit-down interview and missing the work itself.
- Watching a demo of the "proper" process instead of a real day.
- Recording interpretations as if they were observations.
- An agent describing a workflow it has not been given notes for. That is a guess, and
  must be labeled "Draft from assumptions".

## Connects to

Affinity Mapping for synthesis. User Personas and Journey Mapping as outputs. Card
Sorting, when the inquiry shows the product's structure does not match the work.
