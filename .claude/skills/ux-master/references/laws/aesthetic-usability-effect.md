# Aesthetic-Usability Effect

UX Theory card. Audit lens: Visual structure.

Related cards in the deck: [Doherty Threshold](doherty-threshold.md), [Selective Attention](selective-attention.md).

## In one line

People tend to judge a design that looks good as easier to use, whether or not it is.

## What it asks of an interface

- A pleasing design creates a positive first response, and people carry that into their judgment of how well it works.
- People forgive small usability problems more readily in a product that looks good.
- The same effect hides problems. In testing, an attractive design can lead people to say it works well while they struggle with it, so watch what they do as well as what they say.
- Polish is worth doing. It is not a substitute for usability and should come after the functional problems are fixed.

## When it applies

- First impressions: landing pages, onboarding, sign-up, anything a new visitor judges in seconds.
- Design reviews and usability tests of polished mockups.
- Not a justification for visual effects that slow, distract or reduce legibility.

## Detect a violation

**In code**

- Inconsistent visual system: many one-off values for spacing, font size, radius, shadow and color instead of a small set of tokens or variables. Count the distinct values in the styles for the screen.
- Misalignment: sibling elements with different paddings, margins or baselines for no reason.
- Low-contrast text. WCAG 2.2 asks for a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text (success criterion 1.4.3).
- Unstyled or default states: raw browser controls beside custom ones, missing hover, focus and disabled styles.
- Images stretched, cropped badly or missing dimensions so the layout jumps while loading.
- The reverse problem: heavy decoration (gradients, shadows, animation on every element) on a screen whose functional findings are still open.

**In a screenshot or design file**

- Uneven spacing, elements that nearly align, mixed corner radii, more than two or three type sizes with no clear scale.
- Text that is hard to read against its background. WCAG 2.2 asks for a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text (1.4.3). From an image the ratio is an estimate, so say so.
- A screen that looks finished but has open findings in other lenses. Report those first and note that polish may be masking them.

## Example

**Bad:** A sign-up page with seven different font sizes, buttons with three different corner radii and body text in light gray on white.

**Good:** One type scale, one spacing scale, one radius, text that meets contrast minimums, and consistent states on every control.

## When laws conflict

- Against every functional law: aesthetics never outranks a functional problem. Fix P0 and P1 findings from other laws before polish.
- With Von Restorff Effect and Selective Attention: a calm, consistent base is what makes emphasis visible.
- In testing: when what people say and what they do disagree, trust what they do.

## Origin

First studied in human-computer interaction in 1995 by Masaaki Kurosu and Kaori Kashimura of the Hitachi Design Center. They showed 26 variations of an ATM interface to 252 participants and found that ratings of beauty tracked ratings of apparent ease of use more closely than they tracked actual ease of use.

Cite as: Masaaki Kurosu and Kaori Kashimura, Hitachi Design Center (1995).
