# Spot the tells: 25 signs nobody decided

A tell is a decision nobody made: a default filled the gap. Templates, component libraries and AI tools all produce the most common version of a screen, so work made by them is tidy and often hard to use. Use this list as a fast sweep on a screen, slide or page.

Based on the field guide "Spot the Tells" from the Laws of UX bundle (Pip Decks). Questions below are paraphrased for use in this skill.

**How to sweep:** pick one screen (or slide, or page) and one task. Run the checks part by part. Mark each tell with where it is. Fix the worst three first. A tell is a reason to look closer: if a check fails and the work still serves its people, the people win.

For each tell, open the law's card in `laws/` for the numbers, the violation signs and the conflict rules.

## Part 1: Too much to choose from

| # | Tell | Law | Ten-second check |
|---|---|---|---|
| 1 | Seven equal pricing cards (or any set of equal options) | Hick's Law, Analysis Paralysis | Cover the names. Can you still tell which option most people should pick? |
| 2 | Twelve flat navigation items (or a flat agenda, or a flat list of sections) | Chunking, Hick's Law | Look away and name the main sections from memory. |
| 3 | Three primary buttons (or three highlighted callouts) on one screen | Von Restorff Effect | Squint until the text blurs. Count what still stands out. More than one is too many. |
| 4 | Every feature gets equal space | Pareto Principle | What does a regular user do first? Is it the biggest and the closest to the top? |
| 5 | It asks for what it could work out | Tesler's Law | For each field or question: could the system have known this? |

## Part 2: Nothing says where to look

| # | Tell | Law | Ten-second check |
|---|---|---|---|
| 6 | Everything the same visual weight | Selective Attention | Squint. If it becomes one even gray block, there is no hierarchy. |
| 7 | Spacing that groups the wrong things (one gap size everywhere) | Law of Proximity | Blur your eyes and count the clumps. They should match the groups you meant. |
| 8 | Boxes inside boxes inside boxes | Law of Common Region | Count the containers. Would the grouping be unclear without each one? |
| 9 | Looks the same, does different things | Law of Similarity | Point at two look-alike elements. Do they do the same kind of thing? |
| 10 | Decoration on everything (icons over every heading, badges, gradient shapes) | Occam's Razor | Cover one element. Does the screen lose meaning or function? If not, it is decoration. |

## Part 3: Inputs that fight back

| # | Tell | Law | Ten-second check |
|---|---|---|---|
| 11 | A wall of form fields | Cognitive Load | For each field: "We need this now because..." No answer means cut or defer. |
| 12 | Placeholder-only labels | Short-Term Memory, Signifiers | Fill the field. Can you still tell what it asked for? |
| 13 | Formats it refuses to understand | Postel's Law | Paste a phone number with spaces, an email in capitals. Does it cope? |
| 14 | Every field is a plain text box | Constraints | Is there a field with a known set of valid answers that should be a picker? |
| 15 | Tiny tap targets | Fitts' Law | Measure the smallest control on a phone. Compare with the minimums in `defaults.md`. |

## Part 4: Silence after the click

| # | Tell | Law | Ten-second check |
|---|---|---|---|
| 16 | No feedback after a click | Feedback | Press the main button. Does anything change within a moment? |
| 17 | The wait with no end in sight | Doherty Threshold | Is there any wait over about a second without a progress cue? |
| 18 | A long flow with no sense of progress | Goal-Gradient Effect | Can a person say how far along they are and how much is left? |
| 19 | The flow ends on a dead screen (or the deck ends on "Thank you / Questions?") | Peak-End Rule | Does the last moment confirm what happened and offer the next step? |
| 20 | The tour nobody asked for | Paradox of the Active User | Can a person start the real task without clicking through slides of instructions? |

## Part 5: It ignores what people already know

| # | Tell | Law | Ten-second check |
|---|---|---|---|
| 21 | Novel navigation where a convention exists | Jakob's Law | Would someone who has used similar products know where to go? |
| 22 | Labels in the builder's language | Mental Model | Are the words the ones your audience uses, or your org chart's? |
| 23 | Icons with no labels | Signifiers, Law of Closure | Cover the labels you have. Is each icon still unmistakable? |
| 24 | Actions that only appear on hover | Discoverability, Affordances | Is every action reachable with no hover, no right-click, no swipe? |
| 25 | A polished surface on an untested flow | Aesthetic-Usability Effect | Has a real person tried the main task? Polish makes people forgive problems, it does not remove them. |
