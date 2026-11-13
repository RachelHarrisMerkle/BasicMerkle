# Cognitive Dissonance

Psychology Concept card. Audit lens: Expectations.

Related cards in the deck: [Mental Model](mental-model.md), [Jakob's Law](jakobs-law.md).

## In one line

In the deck's interface sense: the discomfort people feel when a control or screen that looks intuitive delivers a result they did not expect.

## What it asks of an interface

- A surprise costs more than a delay. People stop trusting their own reading of the interface, slow down, and may abandon the task.
- The cause is usually a broken promise: a label, icon or layout that says one thing while the behavior says another.
- You find these moments by watching people (interviews, usability tests) and by walking the task step by step and asking at each step "what would a person expect here?"

## When it applies

- Labels and outcomes: buttons, links, toggles, menu items.
- Flows where one step silently changes something from an earlier step.
- Familiar patterns reused with different behavior.

## Detect a violation

**In code**

- A control's label and its handler disagree: "Save" that also publishes, "Next" that submits, "Cancel" that discards without asking, "Back" that leaves the flow.
- Links that open new windows, start downloads or trigger actions with no cue.
- A control that looks like one kind and behaves like another: a checkbox that navigates, a link that deletes, tabs that submit a form.
- Changing one setting silently resets or changes another.
- The same gesture or shortcut doing different things on similar screens.
- Toggles that take effect immediately in some places and need "Save" in others.

**In a screenshot or design file**

- For each labeled control, write down what you expect to happen. Compare with the prototype links or the spec.
- Elements that borrow a familiar look (a search box, a tab bar, a shopping cart icon) for something else.
- A step whose title promises one thing and whose content asks for another.

## Example

**Bad:** A pricing toggle labeled "Annual" that, when switched, also changes the selected plan back to the cheapest tier without saying so.

**Good:** The toggle changes only the prices. The selected plan stays selected and its new price is highlighted briefly so the change is noticed.

## When laws conflict

- Against novelty and delight: predictability wins. Surprise is welcome in content and reward moments, never in controls.
- With Jakob's Law and Mental Model: if a familiar pattern is used, it must behave the familiar way. If you need different behavior, make it look different.

## Origin

The term comes from social psychologist Leon Festinger, whose 1957 book A Theory of Cognitive Dissonance proposed that people are uncomfortable holding inconsistent beliefs and are motivated to reduce the inconsistency. The deck applies the idea to the gap between what an interface appears to promise and what it does.

Cite as: Leon Festinger, A Theory of Cognitive Dissonance (1957).
