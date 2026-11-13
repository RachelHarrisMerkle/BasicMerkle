# Build mode: decide first, then make

Anything people will look at or use goes wrong at the defaults: the first layout that comes to mind, made without deciding who it is for. This mode makes the decision in writing, before the work, where the person can correct it while it is cheap. It adds two short blocks around the work and no new scope.

Applies to any medium: a page, a screen, a component, a slide or deck, a document, an email, a dashboard, a Figma frame.

## Procedure

1. **Look before you make.** Read the request, then whatever exists to build on: existing screens, components, tokens, templates, the brand's deck master, previous decks. Reuse their patterns (Jakob's Law applies inside a product and inside a company too).
2. **Pick the medium guide and the brand regime.** Read the medium guide from the table in SKILL.md, then `../brand/README.md` and the brand files it names for this output. For common interface screens also read the matching playbook in `../flows/`.
3. **Write the UX read** in the format below. If the person can see your messages, send it before the first file write so they can correct it. It always leads your final reply as well.
4. **Make it,** treating each numbered line under "Laws in play" as a constraint.
5. **Run the UX check** against what you made (format below).
6. **Reply** in the shape at the end.

Do not stop to ask questions unless a wrong guess would waste the whole job. State assumptions in the read and carry on.

## The UX read

Under 15 lines. Specific to this piece of work. A read that would fit any screen or any deck is not a read.

```markdown
**UX read**
- **Medium:** <web page | app screen | slide deck | static design | document | email | dashboard>
- **Brand regime:** <digital product | external/marketing | PowerPoint | document/email, with the fonts it sets; see `../brand/README.md`>
- **Audience and goal:** <who is looking at this and what they came to do or decide>
- **Primary action or takeaway:** <the one action, or the one message, this must make easy>
- **Laws in play:**
  1. <Law>: <the concrete constraint it sets here, with a number where one exists>
  2. <three to six laws in all, the ones that would change what you make>
- **Defaults I will not ship:** <two to four named mistakes from defaults.md or tells.md that this invites>
- **States / paths to cover:** <loading, empty, error, success, disabled; or, for a deck, the live-presenting and read-alone versions>
- **Assumptions:** <what you guessed about audience, content, device, setting>
```

For a deck, "primary action" is the decision or belief the audience should leave with, and "states" is how it will be consumed: presented live, sent ahead to be read, or both.

## The UX check

After the work, read it back. Verify each numbered constraint against what is actually there. One row per constraint, same numbers. Cite a line (`file:line`), a slide number, a layer name or a selector, taken from the read-back. If you did not read it back, say so instead of citing a position. "Not held" with a reason is better than a constraint dropped without a word.

```markdown
**UX check**
| # | Law | Result | Where |
|---|---|---|---|
| 1 | <law> | Held | `<file>:<line>` or slide 4 |
| 2 | <law> | Not held: <why, what is left to do> | slide 7 |
| B | Brand | Held / Not held: fonts, tokens or palette, logo, icons, voice, and the regime used | `<file>` or slide 1 |
```

The brand row is always present. Name any brand input that was missing (no `DESIGN.md`, no master template) rather than guessing values.

## Reply shape

1. One or two lines: what you made and where it is.
2. The **UX read**, as written before you started.
3. The **UX check**.
4. Anything the person must replace or decide (placeholder content, open choices).
5. One line offering a full review: "Run a UX audit on this when you want a second pass." Do not run it unasked.

A reply with no UX read has not used this skill.

## Rules

- **The brief wins on content and brand.** If the request itself breaks a law ("show all seven plans", "put the whole contract on one slide"), make what was asked in the least harmful structure and say in one line what you did and why.
- **No scope creep.** Constraints shape what was requested. They do not add features. States (loading, error, empty, success) are part of a feature, not extra scope.
- **No lecture.** The read is for decisions. Keep theory out of the reply unless asked. Justify mode (`justify.md`) writes the reasoning up on request.
- **Small changes get a small read.** For a one-line tweak, one sentence naming the law and the constraint is enough.
- **When laws conflict,** use `../laws/which-law-wins.md`: people can complete the task and are not misled, then they can predict what will happen, then effort is proportionate, then it motivates.
