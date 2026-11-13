# Cognitive Load

Psychology Concept card. Audit lens: Choice and load.

Related cards in the deck: [Hick's Law](hicks-law.md), [Affordances](affordances.md).

## In one line

Cognitive load is the mental effort a person has to spend to understand and use an interface.

## What it asks of an interface

- Mental capacity is limited. When a screen demands more than people have spare, they slow down, miss things and feel overwhelmed.
- Intrinsic load is the effort the task itself needs: holding the goal in mind, taking in new information, keeping track of where you are. You cannot remove it, but you can spread it out.
- Extraneous load is effort spent on things that do not help the task: decoration, inconsistent layout, unclear labels, unnecessary choices. Remove it.
- Working memory holds only a few items at a time. Recent estimates put it at about three or four chunks, lower than the older figure of seven.

## When it applies

- Dense screens: forms, dashboards, settings, pricing comparisons, checkout.
- First use of anything, when everything is new and nothing is automatic yet.
- Not a reason to strip expert tools. People who use a tool daily carry more of it in long-term memory and can handle density that is well organized.

## Detect a violation

**In code**

- One view that mixes several unrelated tasks: more than one form, or several primary actions, rendered together.
- Forms where every field is shown at once, required and optional mixed, with no sections or steps.
- Text blocks used where a short label would do: long instructions above a form, paragraphs inside buttons or table cells.
- Many distinct visual treatments in one view: count the different font sizes, weights, colors and button styles in the styles for that screen. A high count with no system behind it is extraneous load.
- The interface asks people to work something out that the system already knows: totals, time zones, remaining characters, which plan they are on.
- Inconsistent placement of the same control across similar screens.
- Auto-playing media, animation loops or banners that compete with the task.

**In a screenshot or design file**

- Squint at the screen. If no structure survives (no clear groups, no order of importance), load is high.
- Count the things that ask for a decision or an input in one view.
- Decorative elements, icons or illustrations that carry no information next to content that does.
- Instructions that have to be read before the screen can be used.

## Example

**Bad:** A single settings page with 40 controls in one column, each with a paragraph of helper text, under a banner promoting a new feature.

**Good:** The same settings split into five named sections with the common ones first, helper text reduced to one line where it is needed, and advanced options behind a clearly labeled disclosure.

## When laws conflict

- Against Discoverability (show what is possible): reduce load by ordering and grouping first, hiding second. Hide only what is rare.
- Against Tesler's Law: you cannot delete intrinsic load, only move it. Move it to the system (defaults, calculation, memory), not to a later screen.
- Against Aesthetic-Usability Effect: decoration that adds load loses to clarity.

## Origin

Cognitive load theory was developed by educational psychologist John Sweller in the late 1980s, building on George Miller's work on the limits of information processing. Sweller's 1988 paper in Cognitive Science is the usual starting reference.

Cite as: John Sweller, "Cognitive load during problem solving: Effects on learning", Cognitive Science (1988).
