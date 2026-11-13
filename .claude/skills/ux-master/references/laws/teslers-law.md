# Tesler's Law

UX Theory card. Also called: The Law of Conservation of Complexity. Audit lens: Choice and load.

Related cards in the deck: [Postel's Law](postels-law.md), [Cognitive Load](cognitive-load.md).

## In one line

Every process has some complexity that cannot be removed. It can only be moved between the system and the person using it.

## What it asks of an interface

- Some complexity is inherent in the task. Someone has to deal with it.
- Take on as much of it as you can in design and engineering, so people do not have to.
- An hour of the team's work that saves every user a minute is nearly always a good trade.
- Do not simplify to the point of abstraction. An interface stripped so far that people cannot see what it will do has moved complexity back to them.

## When it applies

- Forms and configuration, anything with formats, calculations, dependencies between fields, or setup.
- Defaults, automation, inference and smart suggestions.
- Reviews of "simple" designs that are simple to look at but hard to use.

## Detect a violation

**In code**

- The person does work the system could do: calculating totals, converting units or time zones, typing data the system already has, choosing a card type that the number reveals, picking a country that could be inferred and offered.
- No defaults where a sensible one exists.
- Format rules imposed on input instead of parsing (see Postel's Law).
- Dependent fields that do not update one another: choosing a country does not adjust the state or postal code field.
- Technical choices exposed with no guidance: region, encoding, protocol, cache or sync mode shown to people who cannot judge them.
- Raw system errors passed straight through to the screen.
- The opposite failure: essential controls hidden or removed so the screen looks simple, leaving people unable to predict or steer the result. A single "Go" button with no visible options or summary.
- Automation with no visibility and no override.

**In a screenshot or design file**

- For each field and choice ask "could the product know or work this out?"
- Instructions that tell people how to format or calculate something.
- A very clean screen whose result people could not predict before pressing the button.

## Example

**Bad:** A shipping form that asks for the card type, the full state name typed out and the total weight in grams, and rejects a postal code typed in lowercase.

**Good:** Card type detected from the number, state chosen from a list driven by the postal code, weight calculated from the items, and input normalized before validation.

## When laws conflict

- Against Hick's Law, Occam's Razor and Law of Prägnanz: reduce what is shown, but never delete a decision the task needs. If it must exist, the system should make it by default and let people change it.
- Against Conceptual Model and Feedback: hide the mechanism, not the consequences. When the system decides for people, show what it decided and let them override it.
- Against development cost: complexity moved to the person is paid again by every user on every use.

## Origin

Larry Tesler, a pioneer of interaction design who worked at Xerox PARC and Apple, formulated the law of conservation of complexity in the mid-1980s. He argued that an engineer should spend extra time reducing an application's complexity instead of making millions of users each spend extra time on it. Bruce Tognazzini has added that people tend to use up simplification by attempting harder tasks.

Cite as: Larry Tesler, the law of conservation of complexity (mid-1980s).
