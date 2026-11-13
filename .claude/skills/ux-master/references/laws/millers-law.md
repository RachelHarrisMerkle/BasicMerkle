# Miller's Law

UX Theory card. Audit lens: Choice and load.

Related cards in the deck: [Hick's Law](hicks-law.md), [Chunking](chunking.md).

## In one line

An average person can hold about seven items, give or take two, in working memory.

## What it asks of an interface

- The number is not a design rule. Do not use "seven" to justify limits that the task does not need, such as capping a menu at seven items.
- The useful lesson is chunking: organize content into small meaningful groups so it is easier to process, understand and remember.
- Capacity varies between people and with what they already know and the situation they are in.
- Later research puts the working figure lower, at about four chunks. Both numbers point the same way: do not ask people to keep much in their head.

## When it applies

- Anything people must remember instead of see: codes, steps given in advance, options read aloud, values carried between screens.
- Grouping of long content.
- Does not apply to how many items may be visible in a menu, list or table. Reading from a visible list is recognition, not recall.

## Detect a violation

**In code**

- Instructions that list several steps in advance and then hide them while the steps are carried out.
- Codes, IDs or values people must carry from one view to another (see Short-Term Memory for the checks).
- Long unformatted strings to read or type.
- Long flat sets of anything (fields, options, columns) with no grouping. The fix is grouping, not deletion.
- Misuse to flag in a review: content or navigation arbitrarily cut to seven items or fewer, with needed items hidden as a result.

**In a screenshot or design file**

- Anything the person must remember to complete the task.
- Ungrouped runs of similar items.
- An audit or brief that cites "seven" as the reason to remove needed items.

## Example

**Bad:** A setup screen that says "You will need your account number, routing number, tax ID, business license number and insurance policy number on the next page" and then shows a page with no reminder of which goes where. Separately, a menu cut to seven links with three needed pages moved into an unlabeled "More".

**Good:** Each value is requested with its own labeled field and an example. The menu shows all ten links in three labeled groups.

## When laws conflict

- Against Hick's Law: for choices use Hick's Law, not Miller's. Miller's Law is about memory.
- Against Discoverability and Jakob's Law: never hide a needed or expected item to reach a count.
- With Chunking and Short-Term Memory: these three give the same advice. Cite Chunking for grouping, Short-Term Memory for carrying information, and Miller's Law for the capacity limit behind both.

## Origin

George A. Miller's 1956 paper reported that the span of immediate memory, and of absolute judgment, was limited to about seven items. Miller himself treated the number with some humor, and the paper's lasting point is that recoding information into chunks extends what people can hold. Nelson Cowan's 2001 review argued the limit is closer to four chunks.

Cite as: George A. Miller, "The Magical Number Seven, Plus or Minus Two", Psychological Review (1956).
