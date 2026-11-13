# Analysis Paralysis

Psychology Concept card. Audit lens: Choice and load.

Related cards in the deck: [Hick's Law](hicks-law.md), [Affordances](affordances.md).

## In one line

Analysis paralysis is failing to decide because the decision has been over-thought, often because there are too many options or they are too hard to compare.

## What it asks of an interface

- Too many options can hurt both the decision and how people feel about the whole experience.
- When people need to choose one thing, reduce what they see: feature one option, or give search and filters so they can narrow the set themselves.
- When people need to compare, make comparison easy: put the options side by side with the same attributes in the same order.
- The effect depends on context. It is strongest when options are similar, the differences are hard to judge and the person has no prior preference.

## When it applies

- Pricing tiers, plan pickers, product lists, templates, configuration screens, any "choose one" step.
- Less relevant when people arrive knowing what they want. Then the job is to let them find it fast.

## Detect a violation

**In code**

- A "choose one" set rendered with equal weight and no default, no recommendation and no way to narrow it.
- Options described with different attributes or in a different order, so they cannot be compared row by row: plan cards whose feature lists do not line up.
- Long option lists with no search, filter or sort.
- Differences between options hidden behind tooltips or separate pages.
- Options that differ by one or two small details presented as separate, equal choices.
- No way to see selected items together when comparing across pages.

**In a screenshot or design file**

- For any set of choices: is one recommended, and can you see why?
- Lay two options side by side. Can you list their differences in a few seconds without reading everything?
- More than a handful of near-identical cards in a grid.

## Example

**Bad:** Seven pricing plans in a row, each with a different 12-line feature list in a different order, no plan highlighted and no comparison table.

**Good:** Three plans with one marked "Recommended for most teams", each list showing the same attributes in the same order, and a comparison table for people who want the detail.

## When laws conflict

- Against Tesler's Law (complexity has to live somewhere): do not delete options people need. Reduce what is shown at once and let the system carry the rest through defaults, filters and "see all".
- Against Von Restorff Effect: recommending one option is a use of emphasis. The recommendation has to be honest, meaning it is the best fit for most people who see it, not only the most expensive.
- With Hick's Law: Hick's Law is about time to decide; analysis paralysis is about not deciding at all. The fixes overlap.

## Origin

The phrase "paralysis by analysis" appears in management writing by the 1950s and the idea is far older. The best-known experiment is Iyengar and Lepper's jam study (2000): shoppers offered 24 jams were more likely to stop and look than shoppers offered 6, but far less likely to buy (about 3% compared with about 30%). A 2010 meta-analysis by Scheibehenne, Greifeneder and Todd found the average effect across studies close to zero, so treat choice overload as real but conditional.

Cite as: Sheena Iyengar and Mark Lepper, "When Choice Is Demotivating", Journal of Personality and Social Psychology (2000).
