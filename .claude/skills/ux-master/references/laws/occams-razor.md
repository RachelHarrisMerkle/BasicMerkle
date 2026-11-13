# Occam's Razor

UX Theory card. Audit lens: Choice and load.

Related cards in the deck: [Tesler's Law](teslers-law.md), [Analysis Paralysis](analysis-paralysis.md).

## In one line

Of the explanations or solutions that work equally well, prefer the one that assumes the least.

## What it asks of an interface

- The best way to reduce complexity is not to add it in the first place.
- Go through each element and remove what you can without harming what the screen is for.
- A design is done when nothing more can be removed, not when nothing more can be added.
- The test is "equally well". An element that prevents an error or answers a real question is not excess.

## When it applies

- Reviewing any screen for elements that do not serve its purpose.
- Choosing between two designs or two implementations that meet the same need.
- Feature and option decisions: every setting is an assumption that someone needs it.

## Detect a violation

**In code**

- Elements with no function for the screen's task: decorative icons, repeated headings, badges, dividers, illustrations, duplicate links to the same place.
- Options and settings with no evidence of use, or two controls that do the same thing.
- Extra steps: confirmation pages that confirm nothing, interstitial screens, a "review" step for a single field.
- Fields that are not needed to complete the task (see Principle of Least Effort).
- Custom components where a standard element would do the same job.
- Wrapper elements, modals within modals, tabs with one tab.
- Copy that restates the label or the obvious ("Enter your email in the email field below").

**In a screenshot or design file**

- For each element ask "what would break if this were removed?" If the answer is nothing, flag it as a candidate.
- Two elements that say or do the same thing.
- Decoration competing with content.

## Example

**Bad:** A login card with a welcome illustration, a tagline, a "Sign in to continue" heading, a sub-heading repeating it, social buttons, a divider with "or", two fields, a "Remember me" box, a help link, a sign-up link and a footer.

**Good:** A heading, two labeled fields, a primary button, and links to reset the password and create an account.

## When laws conflict

- Against Signifiers, Feedback and Discoverability: do not remove labels, states or cues. Those work. Remove decoration and duplication.
- Against Jakob's Law: keep an element people expect to find, even if it is rarely used.
- Against Tesler's Law: removing something from the screen does not remove it from the task. If cutting an element moves work to the person, it was not excess.
- Against Short-Term Memory: repeating a value people would otherwise have to remember is not duplication.

## Origin

A principle of parsimony attributed to William of Ockham, an English Franciscan friar and philosopher of the 14th century. It is a rule of thumb for choosing between hypotheses, borrowed by design as an argument for removing what is not needed.

Cite as: Attributed to William of Ockham (c. 1287 to 1347).
