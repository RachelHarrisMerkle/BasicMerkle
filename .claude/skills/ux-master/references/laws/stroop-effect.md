# Stroop Effect

UX Theory card. Audit lens: Signals and feedback.

Related cards in the deck: [Simon Effect](simon-effect.md), [Hick's Law](hicks-law.md).

## In one line

When two attributes of the same thing conflict, people are slower and make more mistakes.

## What it asks of an interface

- Reaction slows when what people see contradicts what they know, like the word "red" printed in blue.
- An element's appearance must fit its job in context. A confirm button and a cancel button side by side must not look the same.
- An element's styling must match its message. A back control should not carry a forward arrow; a success message should not be red.

## When it applies

- Buttons in pairs (confirm and cancel, save and discard), destructive actions, status colors, icons with labels, toggles, alerts.
- Anywhere color, icon, wording and position all describe the same control and could disagree.

## Detect a violation

**In code**

- A destructive action given the primary or success style: "Delete" on the brand's filled button, or in green.
- A safe default (Cancel, Keep) styled as the dangerous one, or the two given identical styles.
- Semantic color contradicting content: an error in green, a success in red, a warning in the brand's neutral color, a "free" label in the error color.
- Icon and label disagreeing: a check mark on "Cancel", a right arrow on "Back", a plus icon on a button that opens a menu, a trash icon on "Archive".
- Toggle state contradictions: the "on" position gray and "off" colored, or a label that reads "Disable" while the switch shows enabled.
- Double negatives in labels and checkboxes ("Uncheck to not receive emails").
- Disabled-looking controls that are active, or the reverse.

**In a screenshot or design file**

- For each control, list what its color, icon, label and position each suggest. Flag any disagreement.
- Pairs of opposite actions that look the same.
- Red or green used on elements that are neither errors nor successes.

## Example

**Bad:** A dialog asking "Delete this project?" with two identical blue buttons, "Cancel" on the right where the confirm action usually sits, and a check-mark icon on it.

**Good:** "Delete project" in the destructive style with a matching label, and "Cancel" as a quieter secondary button in the position the platform uses for cancel.

## When laws conflict

- Against Law of Similarity (consistency): opposite actions must look different even if that adds a button style.
- Against Von Restorff Effect and brand color: semantic colors keep their meaning. Do not use the error color for emphasis or the brand color for destructive actions.
- With Simon Effect: Stroop covers conflicts of meaning (color, icon, word); Simon covers conflicts of position. Check both on every pair of opposite actions.

## Origin

Named for John Ridley Stroop, whose 1935 paper reported that naming the ink color of a color word is slower when the word names a different color. Similar interference had been described in Germany by Erich Jaensch in 1929.

Cite as: John Ridley Stroop, "Studies of interference in serial verbal reactions", Journal of Experimental Psychology (1935).
