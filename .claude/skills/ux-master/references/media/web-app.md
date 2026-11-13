# Medium guide: websites, web apps and mobile apps

The most developed ground in this skill. The playbooks in `../flows/` cover the common screens in detail; this guide covers what is true across all of them.

**Brand:** pick the regime first. Internal or digital product: MDS tokens, Work Sans, Phosphor icons (`../brand/ui.md`). External merkle.com or marketing: Proxima Nova and the existing brand guidelines. Words from `../brand/copy.md`, accessibility from `../brand/accessibility/README.md`, motion from `../brand/motion.md`. See `../brand/README.md`.

Start from the screen type: forms, onboarding, pricing and checkout, navigation, dashboards and tables, and empty/loading/error/success states each have a playbook. Open the one that matches before you build or review.

## First decisions

- **Platform and input.** Touch, pointer or both. Check phone width and desktop width unless told otherwise. Native mobile apps follow their platform's conventions (Jakob's Law is strongest here).
- **Frequency.** A task done once a year should explain itself. A task done fifty times a day should get out of the way. Frequency decides how dense the screen may be.
- **Cost of a mistake.** If it can be undone, favour speed and offer undo. If it cannot, favour a pause and a named confirmation.
- **The one primary action.** Every view has one. Everything else is demoted.

## The laws, as interface decisions

| Law | What it means here |
|---|---|
| Jakob's Law, Mental Model | Use the standard component (select, date picker, checkbox, scrollbar) styled to the brand. Be conventional in structure and controls; be distinctive in content and style. |
| Hick's Law, Chunking | Group long menus under a few labelled headings. Recommend one option in a choice. Do not cut a decision the task needs; reduce what is visible at each step. |
| Fitts' Law | Meet the target minimums in `../defaults.md`, with space between targets. Grow the hit area with padding before the visible size. Keep dangerous buttons normal size but away from the primary action. |
| Feedback, Doherty Threshold | Acknowledge every action within 400 ms: pending, then success or failure. Show progress for long waits. |
| Postel's Law, Constraints | Accept messy input and normalise it. Constrain the choice (a picker) when the valid set is known. Message beside the field, saying how to fix it, input kept. |
| Signifiers, Affordances, Discoverability | Interactive things look interactive; static things do not. Icon plus text unless it is a true convention. No action hidden behind hover, right-click or swipe alone. |
| Law of Proximity, Common Region, Similarity | Less space inside a group than between groups. Border only where spacing is ambiguous. One look per job. |
| Von Restorff, Selective Attention | One high-emphasis element per view or group. Emphasis uses more than colour. |
| Goal-Gradient, Zeigarnik, Peak-End | Multi-step flows show step X of N, allow going back and save progress. The ending confirms what happened and offers the next action. |
| Paradox of the Active User | Teach in place, one thing at a time, when it is needed. Avoid a blocking tour. |
| Cognitive Bias, Campbell's Law | No pre-checked paid extras, no fake urgency, decline as easy as accept. If a metric went up, ask what it stood for. |

## Accessibility is part of the same work

The numbers in `../defaults.md` (contrast, target size, colour never the only cue) are published WCAG and platform figures. Beyond them, check: visible keyboard focus, accessible names on icon-only controls, a reduced-motion alternative, a responsive viewport, and nothing that works only on hover. If an accessibility skill is installed, hand the detailed pass to it.

## Marketing and landing pages

- State what it is and who it is for in the first screen. Make the primary action unmistakable and repeat it, same wording, after each major block.
- Social proof should be specific (a named result) rather than decorative (three matching testimonial boxes).
- Pricing: three plans at most in view, one recommended, the same attributes in the same order; see `../flows/pricing-and-checkout.md`.
- Check at phone width first: equal-card rows become long scrolls.

## Checks before you hand it over

Run the playbook checks for the screen type, then `../tells.md` parts 1 to 5 as a sweep. Count things: options per decision, fields per form, steps per flow, primary buttons per view, the smallest target in pixels. Counts are the cheapest strong evidence.
