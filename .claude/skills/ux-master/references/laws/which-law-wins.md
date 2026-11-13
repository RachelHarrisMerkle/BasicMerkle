# Which law wins

The laws describe different things about people, so they sometimes point in opposite
directions on the same screen. This file gives a rule for deciding.

Use it in three steps:

1. Check that it is a real conflict. Often two laws look opposed but apply to different
   elements, or one of them does not apply to this screen at all.
2. Apply the order of concerns below.
3. If the two laws sit at the same level, find the pair in the table and apply its rule.

Then say in one line which law won and why. A decision you can explain is the point.

## The order of concerns

When two laws conflict, the one that protects the higher concern wins.

| Order | Concern | The question | Cards that mostly serve it |
|---|---|---|---|
| 1 | Completion and honesty | Can people finish the task, and are they free of being misled? | Feedback, Constraints, Fitts' Law (minimum sizes), Postel's Law, Discoverability (of the main action), Cognitive Bias |
| 2 | Predictability | Can people tell what will happen before they act? | Jakob's Law, Mental Model, Conceptual Model, Signifiers, Affordances, Mapping, Stroop Effect, Simon Effect, Cognitive Dissonance |
| 3 | Proportionate effort | Is the work asked of people in line with what they get? | Hick's Law, Cognitive Load, Chunking, Miller's Law, Short-Term Memory, Tesler's Law, Principle of Least Effort, Occam's Razor, Parkinson's Law, Analysis Paralysis, Doherty Threshold, Accot-Zhai Steering Law, the grouping laws |
| 4 | Motivation and memory | Does it keep people going and leave a good memory? | Goal-Gradient Effect, Zeigarnik Effect, Peak-End Rule, Von Restorff Effect, Serial Position Effect, Aesthetic-Usability Effect, Flow |
| 5 | Team practice | Is the team working on the right thing and measuring it well? | Pareto Principle, Campbell's Law |

Two things can change the answer:

- **Who is using it and how often.** For first-time and occasional users, lean toward
  clarity, guidance and fewer choices. For people who use a tool every day, lean toward
  speed, density and fewer interruptions.
- **Whether the action can be undone.** For irreversible or costly actions, lean toward
  constraints and confirmation. For reversible ones, lean toward speed and offer undo.

Level 5 never overrides levels 1 to 4. A metric or a priority call is not a reason to
ship something people cannot use or are misled by.

## Common pairs

| The pull | Looks like | The rule |
|---|---|---|
| Hick's Law against Tesler's Law | "Fewer options" against "the task really has this many decisions" | Do not delete a decision the task needs. Reduce what is visible at each step: set a default, recommend one, put the rest behind a labeled "more". |
| Hick's Law against Discoverability | "Hide it to shorten the menu" against "people need to find it" | Frequent actions stay visible even if the count rises. Rare actions go in one predictable, labeled place. |
| Hick's Law against Principle of Least Effort | "Split into steps" against "fewer clicks" | Minimize total effort, not clicks. Split when each step is a real decision. Keep one screen when the fields are simple and belong together. |
| Hick's Law against Miller's Law | "Cap the menu at seven" | Miller's Law is about memory, not menus. A visible list is read, not remembered. Group long lists; do not cut them to a number. |
| Jakob's Law against Von Restorff Effect | "Follow the convention" against "stand out" | Be conventional in structure and controls, distinctive in content, style and the one thing you want noticed. |
| Jakob's Law against a better new pattern | "People know the old way" against "the new way is faster" | Convention wins unless you can show it fails the task for your users. Then test the new pattern and keep the old path available for a while. |
| Jakob's Law against Serial Position Effect | "Conventional order" against "key items first and last" | Where order is set by convention or logic (alphabetical, chronological, platform button order), keep it and use emphasis instead of position. |
| Law of Similarity against Von Restorff Effect | "Make it consistent" against "make it different" | Consistency is the baseline. One element per view or group may break it. |
| Law of Similarity against Stroop Effect | "One button style" against "opposite actions must differ" | Opposite actions get different styles, even if that adds a variant. |
| Law of Similarity against Affordances | "Same look everywhere" against "show what is clickable" | Interactive and static elements never share a look. |
| Occam's Razor against Signifiers | "Remove elements" against "label things" | Remove decoration and duplication. Keep anything that tells people what a control does or what happened. |
| Occam's Razor against Feedback | "Fewer states to build" against "show what happened" | Loading, error, empty and success states are part of the screen, not extras. |
| Occam's Razor against Short-Term Memory | "Do not repeat information" against "do not make people remember" | Repeating a value people would otherwise have to carry in their head is not duplication. |
| Law of Prägnanz against Law of Common Region | "Fewer boxes" against "group with a boundary" | Group with spacing first. Add a border or background only where spacing alone is ambiguous. |
| Law of Closure against Signifiers | "A simple icon is enough" against "say what it does" | Closure can hint, not explain. Important or irreversible actions get a text label. |
| Postel's Law against Constraints | "Accept anything" against "prevent invalid input" | Constrain the choice when the valid set is known (a picker, a select). Be liberal with format when people type freely. |
| Feedback against Flow | "Confirm and announce" against "do not interrupt" | Use the quietest feedback that works. Undo beats a confirmation dialog for anything reversible. Confirm only irreversible, costly actions. |
| Constraints against Flow | "Add a safety step" against "keep people moving" | Same rule: friction in proportion to the cost of a mistake. |
| Fitts' Law against error prevention | "Big and close" against "hard to hit by accident" | Do not shrink a dangerous button. Keep it a normal size, move it away from the primary action and style it differently. |
| Fitts' Law against density | "Large targets" against "fit more on screen" | On touch, target size wins. On pointer-driven expert tools, compact is acceptable down to the WCAG 2.2 AA floor of 24 by 24 CSS pixels with adequate spacing. |
| Fitts' Law against Mapping or Simon Effect | "Put it where it is fastest to reach" against "put it next to what it affects" | Keep the control with its effect. If reach suffers, add a second copy where reach matters. |
| Doherty Threshold against purposeful delay | "Respond fast" against "a short wait can build trust" | Acknowledge within 400 ms, always. Only the final result of a high-stakes process may be held back briefly, and never to show a sales message. |
| Doherty Threshold against Peak-End Rule | "Be quick" against "add a moment of delight" | Speed wins for anything people do often. Save designed moments for rare milestones. |
| Peak-End Rule against Parkinson's Law | "A memorable ending" against "do not lengthen the task" | The ending must not add work. Improve the last step that already exists. |
| Goal-Gradient Effect against Cognitive Bias | "Show progress to motivate" against "do not mislead" | Progress must be true. Credit steps the person has really done. Never show a bar that misstates how much is left. |
| Zeigarnik Effect against Selective Attention | "Remind people of unfinished tasks" against "do not distract" | Remind only for tasks the person started and benefits from finishing, and let them dismiss it. |
| Von Restorff Effect against Selective Attention | "Make it loud" against "banners get ignored" | Emphasize inside the layout with size, weight and position. Things styled like ads are skipped. |
| Von Restorff Effect against Cognitive Bias | "Highlight a plan" against "do not steer" | The highlighted option must be the best fit for most people who see it, not only the most profitable. |
| Selective Attention against Discoverability | "Keep the screen quiet" against "show what is possible" | The current task's actions are prominent. Everything else is findable, not prominent. |
| Paradox of the Active User against Discoverability | "Nobody reads instructions" against "people must learn the product" | Teach in place, one thing at a time, at the moment it is needed. No blocking tours. |
| Chunking against Principle of Least Effort | "Break it into parts" against "keep it short" | Use visible sections on one page for parts of one decision. Use separate steps for separate decisions. |
| Cognitive Load against expert density | "Show less" against "experts want it all" | For daily-use tools, density is fine when it is organized. Reduce extraneous load (decoration, inconsistency), not information. |
| Aesthetic-Usability Effect against any functional law | "It looks better this way" | A functional law always wins. Polish comes after the functional findings are closed. |
| Tesler's Law against Conceptual Model | "Let the system decide" against "people must understand what happened" | Hide the mechanism, not the consequence. Show what the system decided and let people change it. |
| Pareto Principle against Postel's Law | "Serve the common case" against "handle every input" | Pareto sets the order of work. It does not excuse failing uncommon inputs or people. |
| Campbell's Law against a metric-led design | "The number went up" | Ask what the number stood for. If the change helps the number and hurts the task, the task wins. |

## When the table does not cover it

Ask three questions in order and stop at the first one that separates the options:

1. Which option lets more people complete the task without being misled?
2. Which option is easier to predict before acting?
3. Which option asks for less effort over the whole task, not just this screen?

If the answer is still unclear, it is a question for evidence, not for argument. Say so,
and propose the cheapest test: usually five minutes watching someone try both. The
`../methods/usability-test.md` has the usability test workflow.
