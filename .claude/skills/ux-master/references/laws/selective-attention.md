# Selective Attention

Psychology Concept card. Audit lens: Focus.

Related cards in the deck: [Doherty Threshold](doherty-threshold.md), [Signifiers](signifiers.md).

## In one line

People attend to a small part of what is in front of them, usually the part related to their current goal, and filter out the rest.

## What it asks of an interface

- Attention is a filter. People are not being careless when they miss something outside their task; that is how attention works.
- Design has to guide attention to what matters at that moment and keep everything else quiet.
- Banner blindness: people skip content that looks like an ad or sits where ads usually sit, even when it is important.
- Change blindness: people miss a change on screen when nothing draws the eye to it, or when another change happens at the same moment.

## When it applies

- Alerts, validation messages, promotions, status changes, live updates.
- Any screen with more than one thing competing for first look.
- Updates that happen away from where the person is looking.

## Detect a violation

**In code**

- Important messages rendered in banner-like containers at the top of the page or in a side rail, styled like promotions.
- State changes that happen away from the control that caused them, with no transition, highlight or announcement: a total that updates at the bottom of a long page, a list that reorders silently, an error summary far from the field.
- Several things changing at once after one action.
- More than one element with the strongest visual treatment in a view: several filled primary buttons, several badges, several animated elements.
- Auto-advancing carousels, looping animation or video near the task.
- Toasts or notices that disappear on a short timer and cannot be seen again.
- Live updates with no announcement for assistive technology (`aria-live` or the native equivalent).

**In a screenshot or design file**

- Where does the eye land first, second and third? If the first is not the most important thing for the task, flag it.
- Critical information in a colored box that resembles an ad or cookie banner.
- Multiple high-contrast, saturated or moving elements in one view.
- Before and after frames of an interaction: can you spot what changed within a second?

## Example

**Bad:** A payment form where the "Card declined" message appears in a pale banner at the very top of a long page, above a rotating promotion, while the person is looking at the Pay button.

**Good:** The message appears next to the card field, the field is outlined and the page scrolls it into view. The promotion is removed from the checkout altogether.

## When laws conflict

- Against Von Restorff Effect: emphasis only works when it is rare. One emphasized element per view; if two things need attention, order them, do not style both loudly.
- Against Discoverability: features that do not serve the current task should be findable, not prominent.
- Against business requests to promote on task screens: the task wins on task screens.

## Origin

The modern study of selective attention began with Colin Cherry's 1953 work on how people follow one voice among many, and Donald Broadbent's 1958 filter model, which proposed that limited processing capacity forces early selection of what to attend to. The term "banner blindness" comes from Benway and Lane (1998).

Cite as: Colin Cherry (1953) and Donald Broadbent's filter model (1958).
