# Short-Term Memory

Psychology Concept card. Audit lens: Choice and load.

Related cards in the deck: [Affordances](affordances.md).

## In one line

Short-term memory holds a small amount of information for a short time. Interfaces should not depend on it.

## What it asks of an interface

- Capacity and duration are both limited. The deck gives about seven chunks, each fading after 20 to 30 seconds without rehearsal; later research suggests about four chunks is a safer working figure.
- People are much better at recognizing something in front of them than recalling it from memory. Show options instead of asking people to remember them.
- Mark what has already been seen or done: visited links, completed steps, breadcrumbs.
- Put the burden of remembering on the system. Carry information forward between screens instead of asking people to hold it.

## When it applies

- Multi-step flows, comparisons, verification codes, search and filter, anything that spans more than one screen.
- Command-style interfaces and forms where a required format or value has to be remembered.

## Detect a violation

**In code**

- Information shown on one screen that must be typed or chosen on another: a code, an ID, a price, a selected option. Check whether earlier choices are passed forward and displayed.
- Placeholder used as the only label or the only format hint, so it disappears while typing.
- Filters, sort order or search terms applied but not shown, or lost on navigation.
- Comparison that requires switching between pages or tabs with no side-by-side view or pinned selection.
- Multi-step flows with no summary of earlier answers and no way to review before submit.
- Validation rules shown only after failure, so people must remember them for the retry. Passwords are the usual case.
- Visited links styled the same as unvisited ones in a long list of destinations; no breadcrumb or "you are here" cue in deep navigation.
- One-time codes that cannot be pasted or auto-filled (`autocomplete="one-time-code"` missing on the web).

**In a screenshot or design file**

- For each input, ask "where does the person get this value from?" If the answer is another screen, flag it.
- Steps in a flow that do not show what was chosen earlier.
- Active filters with no visible chips or summary.
- Password rules or format requirements that are not visible while typing.

## Example

**Bad:** A checkout that shows a discount code on the cart page and asks for it to be typed from memory on the payment page, with password rules revealed only after a failed attempt.

**Good:** The applied discount is carried through and displayed on every step. Password rules are listed beside the field and tick off as each is met.

## When laws conflict

- Against Occam's Razor and Law of Prägnanz (remove repeated information): repeating a value people would otherwise have to remember is not redundancy.
- Against Miller's Law misuse: the limit is about what people must hold in their heads, not about how many items may appear on a screen. Recognition from a visible list is cheap.

## Origin

The split between short-term and long-term memory dates from the 19th century. The best-known account is the modal model published by Richard Atkinson and Richard Shiffrin in 1968. George Miller's 1956 paper gave the "seven, plus or minus two" capacity estimate; Nelson Cowan's 2001 review argued for about four chunks.

Cite as: Richard Atkinson and Richard Shiffrin, the modal model of memory (1968).
