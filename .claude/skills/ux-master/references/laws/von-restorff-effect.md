# Von Restorff Effect

UX Theory card. Also called: The Isolation Effect. Audit lens: Focus.

Related cards in the deck: [Law of Similarity](law-of-similarity.md), [Selective Attention](selective-attention.md).

## In one line

When several similar things are shown together, the one that differs is the one most likely to be remembered.

## What it asks of an interface

- Make the most important information or action visually distinct from what surrounds it.
- Use emphasis sparingly. If several things are emphasized they compete, and heavily emphasized items can be mistaken for ads and ignored.
- Do not rely on color alone to create the difference. People with color vision deficiency or low vision need a second cue such as size, weight, position, shape, an icon or a label.
- Be careful with motion as the distinguishing cue. Some people are sensitive to it.

## When it applies

- Primary call to action, recommended option in a set, critical warnings, new or changed items, the current step or selection.
- Any group of similar items where one matters more.

## Detect a violation

**In code**

- No distinct primary action: every button in a view uses the same variant, or the main action is styled as secondary.
- Too many: more than one high-emphasis button, badge or highlight competing in one view. Count the elements using the strongest style.
- A set of options (plans, cards, tiles) where the recommended one has the same styles as the rest.
- Difference carried by color only: status, selection, errors or the recommended item marked with a hue change and nothing else. WCAG 2.2 success criterion 1.4.1 requires that color is not the only visual means of conveying information.
- Weak difference: emphasis that does not meet the 3:1 contrast WCAG 2.2 asks of user interface components (success criterion 1.4.11), or differs from its neighbors only slightly.
- Attention-seeking animation with no reduced-motion alternative (`prefers-reduced-motion` or the platform setting).
- Emphasis on the wrong thing: the loudest element is a promotion, a secondary action or decoration.

**In a screenshot or design file**

- Convert to grayscale in your head. Does the important element still stand out?
- Count the loud elements. There should be one per view or per group.
- Check what the loudest element is. It should be the thing the person came to do.

## Example

**Bad:** A pricing page with three identical gray cards and identical outline buttons. A second version where every card has a colored "Best value", "Most popular" or "New" ribbon.

**Good:** One plan is larger, has a filled button and a "Recommended" label in text. The other plans share a quieter style.

## When laws conflict

- Against Law of Similarity: consistency is the baseline that makes one exception visible. One exception per group.
- Against Selective Attention (banner blindness): emphasis that looks like advertising gets ignored. Emphasize with size, weight and position inside the layout, not with banners.
- Against Jakob's Law: be distinctive in emphasis, conventional in structure. Do not move or restyle a standard control beyond recognition to make it stand out.
- Against Cognitive Bias: the emphasized option must be the one that suits most people, not only the one that earns the most.

## Origin

German psychiatrist and pediatrician Hedwig von Restorff reported in a 1933 study that when people were shown a list of similar items with one item that differed, they remembered the different item better. The finding is also called the isolation effect.

Cite as: Hedwig von Restorff (1933).
