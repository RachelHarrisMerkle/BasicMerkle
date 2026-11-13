# Pareto Principle

UX Theory card. Also called: The 80/20 Rule. Audit lens: Focus.

Related cards in the deck: [Parkinson's Law](parkinsons-law.md), [Analysis Paralysis](analysis-paralysis.md).

## In one line

In many situations a small share of the causes produces a large share of the effects, often summarized as 80% from 20%.

## What it asks of an interface

- Inputs and results are rarely spread evenly.
- In a large set, a few items usually account for most of the value: a few features carry most of the usage, a few problems cause most of the complaints.
- Spend most of the effort where it helps the most people most.
- The 80 and 20 are a pattern, not a measurement. Find the real distribution in your own data.

## When it applies

- Prioritizing audit findings and fixes.
- Layout: which actions and content get the prominent positions.
- Scope: which features a first version needs.
- Not a license to ignore the rest. Accessibility, error states and edge cases still have to work.

## Detect a violation

**In code**

- No visual priority among features: every action, card or tile given equal size and position, with the most-used ones not first.
- The most common task takes more steps than a rare one.
- Defaults that suit a rare case, so most people have to change them.
- Dashboards showing every available metric at equal weight.
- Settings and options ordered alphabetically or by implementation order where frequency of use would serve better.
- In a review: a long flat list of findings with no order of importance.

**In a screenshot or design file**

- Identify the one or two things most people come to this screen to do. Are they the most prominent and the quickest to reach?
- Grids of equal tiles where usage is clearly unequal.
- Rare or advanced options sitting in prime positions.

## Example

**Bad:** An account page where "Download invoice", the reason most people visit, is the ninth of twelve equally sized links.

**Good:** "Download latest invoice" is the primary button at the top. Less common actions are grouped under clear headings below.

## When laws conflict

- Against Postel's Law and accessibility: prioritizing the common case never justifies breaking the uncommon one. Pareto orders the work; it does not excuse exclusion.
- Against Jakob's Law and Serial Position Effect: where a list has a conventional order, keep the order and use emphasis to mark what is used most.
- With Hick's Law and Selective Attention: Pareto tells you which option to recommend and which content gets attention.

## Origin

Named for economist Vilfredo Pareto, who observed around 1900 that roughly 80% of the land in Italy was owned by 20% of the population. Quality-management pioneer Joseph Juran later generalized the pattern and gave it Pareto's name.

Cite as: Named for Vilfredo Pareto; generalized by Joseph Juran.
