# Workflow: card sorting

Participants sort topics into groups and name them. The result shows how users expect a
product's content to be organized and what they would call each part. Use it before
building or restructuring navigation, categories, settings or a help center (Hick's Law,
Chunking, Mental Model).

## Plan

Ask for, or infer and confirm:

- **What is being organized:** navigation, a product catalog, settings, help articles.
- **The type of sort:**
  - *Open:* participants make and name their own groups. Use it to discover a structure.
  - *Closed:* participants sort into groups you provide. Use it to test a structure.
  - *Hybrid:* your groups, and they may add their own.
- **Who the participants are** and how the sort will run: in person with paper cards, or
  remote with an online tool or a shared board.

Produce a one-page plan:

```markdown
# Card sort plan: <what is being organized>

**Goal:** <what structure decision this informs>
**Type:** <open, closed or hybrid>
**Cards:** <how many, drawn from where>
**Participants:** <who, how many, how recruited>
**Format:** <in person or remote, moderated or not, time per session>
```

On numbers: Jakob Nielsen's guidance, based on a study by Tullis and Wood, is about 15
participants for a card sort, more than for a usability test because the result is a
pattern across people. As a working heuristic, 30 to 60 cards keeps a session manageable.

## Prepare

1. **Build the card list.** If you have the product's code or site map, extract the
   destinations and items from it, then:
   - Write each card as content, not as a current menu label, so the wording does not
     dictate the grouping. "See what you were charged last month", not "Billing".
   - Keep cards at the same level of detail.
   - Remove duplicates and cards that are really categories.
   - Avoid shared words that make cards group by wording alone.
2. **Write the session script,** following the card's four steps:
   - *Gather:* hand over the shuffled cards.
   - *Sort:* "Put these into groups that make sense to you. There is no right answer.
     Please think aloud." Allow an "unsure" pile.
   - *Label:* "Give each group a name."
   - *Dig deeper:* "Why do these go together?" "Which were hard to place?" "Is anything
     missing?"
3. **Produce a recording sheet** per participant: group name, cards in it, comments,
   cards left unsorted.

Output the numbered card list, the script and the sheet, ready to print or paste into a
tool.

## Run

People run the sessions. The agent does not sort the cards on the participants' behalf.
If the user wants a starting structure before research, produce a "Draft from
assumptions" grouping and say that it reflects how the agent reads the content, not how
users do.

## Synthesize

When the user brings back each participant's groups and labels:

1. **Normalize labels.** Merge names that clearly mean the same thing and record the
   variants: they are the vocabulary.
2. **Count pairings.** For each pair of cards, count how many participants put them in
   the same group. Present it as a table of the strongest pairs, or as clusters.
3. **Find the clusters** most participants agree on. These are safe groups.
4. **Find the split cards:** cards placed in different groups by different people, and
   cards often left unsorted. These need a clearer name, two homes, or a rethink.
5. **Choose group names** from the labels participants used most.
6. **Propose a structure** and state how strong the agreement behind each group is.

Output:

```markdown
# Card sort results: <what was organized>

**Participants:** <n>, <type of sort>, <dates>

## Proposed structure
| Group (label participants used most) | Cards | Agreement |
|---|---|---|
| <name> | <cards> | <n of n participants grouped these together> |

## Cards without a clear home
| Card | Where people put it | Recommendation |
|---|---|---|

## Vocabulary
| Concept | Labels participants used |
|---|---|

## Next step
<test the proposed structure with find-it tasks in a usability test or a tree test>
```

Show the counts. Do not report a structure as "what users want" when agreement was low.

## Pitfalls

- Cards written in the current menu's words, which reproduces the current menu.
- Too many cards, so participants tire and rush.
- Treating one participant's sort as the answer.
- Skipping the "why". The reasons explain the split cards.
- An agent's own sort presented as a result.

## Connects to

Usability Test to check that people can find things in the new structure. Contextual
Inquiry when the groupings depend on how people work. The navigation playbook in
the playbooks in `../flows/`.
