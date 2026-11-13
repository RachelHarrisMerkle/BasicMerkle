# Goal-Gradient Effect

UX Theory card. Audit lens: Progress and endings.

Related cards in the deck: [Zeigarnik Effect](zeigarnik-effect.md), [Selective Attention](selective-attention.md).

## In one line

People speed up and try harder the closer they get to a goal.

## What it asks of an interface

- Being near the end motivates. Show people how close they are.
- Clear progress indicators help people finish multi-step tasks.
- Progress that is already credited at the start makes people more likely to continue. This is often called endowed or artificial progress.
- Use credited progress honestly: count steps the person has completed, such as creating the account, not invented ones.

## When it applies

- Multi-step forms, onboarding, checkout, profile completion, setup checklists, loyalty and reward schemes, long uploads or imports.
- Not relevant to single-step actions or open-ended tools with no finish line.

## Detect a violation

**In code**

- A flow with more than one step and no step indicator: no "Step 2 of 4", progress bar or checklist. Look for step state (an index, a route per step, a wizard component) with nothing rendering it.
- Progress indicators that do not match reality: a fixed-width bar, a total step count that changes midway, a bar that reaches the end before the last step.
- Long flows where the hardest step comes last with no warning.
- Setup checklists that start at zero when the person has already done something that counts.
- No estimate of remaining effort for long tasks ("About 2 minutes left", "3 questions to go").
- The final step looks the same as the others, so nothing signals "last one".

**In a screenshot or design file**

- For any flow of two or more screens: can you tell from any one screen where you are and how much is left?
- Progress bars with no labels or steps.
- A flow whose last screen does not look like an ending.

## Example

**Bad:** A five-screen onboarding with only a "Next" button on each screen and no indication of how many screens remain.

**Good:** "Step 3 of 5" with named steps, the account-creation step already ticked, and the last step labeled "Finish setup".

## When laws conflict

- Against Cognitive Bias (honesty): progress must be true. Crediting a real completed step is fine. A bar that jumps to 80% to keep someone in a flow that is nowhere near done is deception, and it backfires when the remaining steps turn out to be long.
- Against Occam's Razor (remove elements): a progress indicator earns its place in any flow of three or more steps. For two short steps it is optional.
- Against Principle of Least Effort: if the indicator shows a long road, shorten the road. Do not hide the indicator.

## Origin

Behaviorist Clark Hull proposed the goal-gradient hypothesis in 1932 and reported in 1934 that rats ran faster as they neared food at the end of a runway. Kivetz, Urminsky and Zheng (2006) showed the pattern in human reward programs. In a related car-wash study by Nunes and Drèze (2006), 34% of customers given a 10-stamp card with 2 stamps already filled completed it, compared with 19% given an empty 8-stamp card needing the same number of purchases.

Cite as: Clark Hull (1932); Ran Kivetz, Oleg Urminsky and Yuhuang Zheng (2006).
