# Jakob's Law

UX Theory card. Audit lens: Expectations.

Related cards in the deck: [Mental Model](mental-model.md), [Occam's Razor](occams-razor.md).

## In one line

People spend most of their time on other products, so they expect yours to work the way those do.

## What it asks of an interface

- People bring expectations from familiar products to any new one that looks similar.
- Using patterns people already know lets them spend their effort on the task, not on learning the interface.
- When you must change something familiar, soften the change. Let people keep the old version for a limited time, or guide them to what moved.

## When it applies

- Structure and standard components: navigation, search, forms, carts, checkout, settings, dialogs, tables, media controls.
- Platform conventions: system gestures, keyboard shortcuts, standard control placement on web, iOS, Android and desktop.
- Not a ban on new ideas. It sets the burden of proof: a new pattern has to be clearly better at the task, not only different.

## Detect a violation

**In code**

- Custom replacements for standard controls: hand-built selects, checkboxes, date pickers, scrollbars, text inputs or video controls that drop expected behavior (keyboard support, focus, native pickers on mobile).
- Broken web conventions: logo not linking home, links that are not `<a>` elements (so open in new tab and copy link fail), buttons that are not buttons, back button broken by client-side state, no visible focus, scroll hijacking, right-click disabled.
- Standard placement ignored: search not in the header, account and cart not top right in a left-to-right store, primary navigation in an unusual place, form submit not at the end of the form.
- Standard meaning ignored: an icon with a strong conventional meaning (magnifier, gear, trash, house, heart) used for something else.
- Platform patterns mixed: an iOS-style back gesture pattern in an Android app, or web patterns inside a native app.
- A redesign with no transition: old URLs break, moved features have no pointer, no option to switch back for a while.

**In a screenshot or design file**

- Name the category of product, then list what its best-known examples all do. Check each against the screen.
- Familiar controls in unfamiliar places.
- Controls that look custom where a standard one would work.

## Example

**Bad:** A checkout with a custom-drawn dropdown that does not respond to the keyboard, a "Continue" button at the top left and a cart icon that opens the wishlist.

**Good:** Native or standards-compliant controls, the primary button at the end of the form, and icons used for their usual meanings.

## When laws conflict

- Against Von Restorff Effect and brand distinctiveness: follow convention for structure and controls; be distinctive in content, visual style and the one thing the product does differently.
- Against Serial Position Effect: when a list has a conventional or logical order, keep it. Do not reorder to put key items at the ends.
- Against Hick's Law and Occam's Razor: do not remove a conventional element people will look for only to reduce the count.
- Convention loses only when you can show it fails the task for your users. Then test the alternative and help people through the change.

## Origin

Stated by usability researcher Jakob Nielsen in 2000 as the "law of the internet user experience". Nielsen co-founded the Nielsen Norman Group with Don Norman and is known for discount usability methods and heuristic evaluation.

Cite as: Jakob Nielsen, Nielsen Norman Group (2000).
