# Medium guide: presentations and slide decks

A deck is an interface the audience cannot click. They cannot slow down, go back or skim ahead, and in a live room they cannot ask what a word means. That raises the cost of every extra word and every unclear emphasis. These notes translate the laws for slides.

**Brand:** Merkle deck regime (legacy brand, `Merkle_2025_v2`, Arial or Proxima Nova, wordmark rules). Read `../brand/pptx/README.md` and `../brand/pptx/brand-guidelines.md`; words from `../brand/copy.md`. The Merkle master template is not bundled, ask for it before rebuilding or creating a deck. The brand's rules (left-aligned headlines, eyebrow labels, no decorative lines under titles) agree with the laws below.

Two consumption modes need different decks: **presented live** (the speaker carries the detail, slides carry the point) and **read alone** (sent ahead, the slide must stand on its own). Decide which, or build the read-alone version and say so. Do not put a read-alone density on a screen you will talk over.

For the mechanics of building a `.pptx` (layouts, placeholders, export), follow `../brand/pptx/` for the build approach (patch or rebuild, font choice, theme, QA); the brand file asks the person to choose Arial or Proxima Nova, which overrides the "do not ask" default in build mode. This guide decides what goes on the slide, not how the file is assembled.

## The laws, as slide decisions

| Law | What it means on a slide |
|---|---|
| Cognitive Load, Occam's Razor | One message per slide. Write the title as the message ("Churn fell 18% after onboarding changed"), not the topic ("Churn"). Cut every element the message does not need. |
| Chunking, Miller's Law | Group a long list into a few labelled chunks instead of cutting it to a number. Miller's Law is about what people hold in memory, not how many bullets are allowed. A slide the audience must remember across is a memory test. |
| Hick's Law, Analysis Paralysis | Decision slides show few options, with a recommendation, and the same attributes for each in the same order. Put the full comparison in an appendix. |
| Von Restorff Effect, Selective Attention | One emphasized thing per slide: the number, the phrase, the bar. If three things are bold, nothing is. Use size and position, not only colour. |
| Serial Position Effect | The first and last items are remembered best. Open and close with what matters most; put the supporting detail in the middle. Same for the order of slides and the order of bullets. |
| Peak-End Rule | The last slide is the part people take away. End on the decision, the ask or the next step with an owner and a date, not "Thank you" or "Questions?". Make the strongest moment deliberate. |
| Law of Proximity, Common Region, Similarity, Continuity | Space groups things: a label sits closer to its own chart than to the next. Same-role elements look the same on every slide (titles, callouts, sources). Align to a grid so the eye has a path. Use a box only where spacing alone is ambiguous. |
| Short-Term Memory | Repeat the number that matters instead of saying "as on slide 3". Label chart lines directly rather than with a legend people must keep decoding. |
| Goal-Gradient, Zeigarnik | Long decks need signposts: an agenda early, a visible section marker, a "where we are" cue. People tolerate length they can see the end of. |
| Jakob's Law, Mental Model | Use familiar structure: title, why now, the answer, the evidence, the ask. Use the audience's words, not internal acronyms. |
| Doherty Threshold | Animations and builds are waits. A transition or build that makes people wait to see the next thing costs more than it gives. Default to none. |
| Fitts' Law | Applies only to clickable decks: on-screen navigation, links and buttons need touch-sized targets (see `../defaults.md`). |
| Cognitive Bias, Campbell's Law | Charts must not mislead: honest axes, a stated baseline, no cherry-picked windows. A recommended option must be the best fit, not the most convenient one. Do not design slides to hit a metric of "looks impressive". |
| Aesthetic-Usability Effect | Polish makes people forgive a muddled story. It does not fix one. Fix the structure first, then the finish. |

## Working heuristics (not published standards)

These come from common presentation practice, not from a named source. Treat them as starting points and say so if you quote them.

- Projected body text: aim for about 24 pt or larger; treat 18 pt as the floor, and do not shrink text to make more fit. If it needs smaller type, it belongs in a handout or appendix.
- One idea per slide, one visual focal point, a sentence-length title.
- Contrast: use the published WCAG figures in `../defaults.md` (4.5:1 body, 3:1 large text and graphics), and check on a projector-like dim screen if you can.
- Notes: put the detail the speaker says in the speaker notes. If a slide is a wall of words, the audience reads instead of listening.

## Defaults to avoid (deck versions of the tells)

- **The bullet wall.** Paragraphs as bullets. Make it a sentence title plus one visual, or split it.
- **The agenda soup.** Twelve topic slides with no hierarchy. Group into three or four sections.
- **Equal-weight everything.** Six equal icons in a row (the deck version of the equal-cards grid). Pick the one or two that matter.
- **The logo-and-icon decoration.** An icon over every heading. Remove it if the slide loses nothing.
- **The dead ending.** "Thank you" as the last slide. End on the ask.
- **The legend decode.** Colour keys the audience must match across the slide. Label directly.
- **The unreadable chart.** Dense table pasted as an image. Show the one comparison that matters, link or append the rest.
- **The colour-only signal.** Red/green status with no label or icon. Add a second cue.

## Checks before you hand it over

1. Read only the slide titles in order. Do they tell the story? (If not, the structure is the problem.)
2. Squint at each slide. Is there one clear focal point?
3. For each slide: what should the audience leave this slide knowing, and can they tell in five seconds?
4. Does the last slide say what happens next, who does it, and by when?
5. Is any number, term or acronym used before it is explained?
6. Would the deck survive being read with no speaker? If it must, is the density right for that?
