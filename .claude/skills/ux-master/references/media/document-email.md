# Medium guide: documents, reports, proposals and email

Readers scan before they read, and they read in interrupted bursts. The same laws that shape a screen shape a page.

**Brand:** the bundled Merkle sources do not set document or email rules. Default to the deck look (Proxima Nova, Arial as the safe fallback for outside audiences), say it is an assumption and ask the person to confirm. Voice from `../brand/copy.md`; see `../brand/README.md`.

## The laws, as writing and layout decisions

| Law | What it means on the page |
|---|---|
| Serial Position Effect, Peak-End Rule | Put the conclusion, decision or ask first (inverted pyramid) and end on the next step. The middle is where detail lives and where attention is lowest. |
| Cognitive Load, Chunking | Short sections under headings written as statements. Short paragraphs. Lists for parallel items, prose for reasoning. A table only when the reader will compare. |
| Selective Attention, Von Restorff | One bolded phrase per paragraph at most. One call to action per email, visibly distinct from the surrounding text. |
| Hick's Law | Do not offer five links or three requests in one email. One ask, or a clear first ask. |
| Law of Proximity, Common Region | Spacing shows which caption, number or note belongs to which block. Do not box everything. |
| Short-Term Memory | Do not make the reader recall a figure from page two. Repeat it where it is used. Define a term where it first appears. |
| Goal-Gradient, Zeigarnik | In a long document, a contents list, section numbers and a short "what this covers" at the top let the reader see the end. |
| Jakob's Law, Mental Model | Use the standard structure for the genre (summary, context, options, recommendation, next steps) and the reader's own vocabulary. |
| Fitts' Law | In email, buttons and links need touch-sized targets with space around them (see `../defaults.md`). |
| Postel's Law | If readers reply with data (dates, names, IDs), accept the formats they will use. |
| Cognitive Bias | Present options fairly; do not bury the cost or the downside. Subject lines say what the message is. |

## Working heuristics (not published standards)

- Subject line or title states the message or the ask, not the topic.
- Line length of roughly 50 to 75 characters is a widely used comfort range for body text. Label it as a heuristic when quoted.
- The first two sentences of an email should let the reader decide whether to read on.
- For published thresholds on contrast and target size, use `../defaults.md`.

## Accessibility

Real text rather than text in images, meaningful link text ("view the Q3 report", not "click here"), alt text for images that carry meaning, contrast per `../defaults.md`, heading levels in order, and no meaning carried by colour alone.

## Checks before you hand it over

1. Read only the headings (or subject plus first line). Does the story survive?
2. Can the reader tell in five seconds what you want from them?
3. Is there one primary ask?
4. Does the document end on what happens next, who does it and by when?
5. Is there anything the reader must remember from earlier to understand later?
