# Default mistakes and numbers to build to

Mistakes that appear when nobody decides. They were named for interfaces, but each has a counterpart in decks, documents and emails (see the medium guides). Check the list against whatever is in front of you.


These are the things an agent builds when it does not decide. Each has a name so you can
say which ones you are avoiding. Check the list against the screen in front of you.

| Name | What gets built by default | Law it breaks | Build this instead |
|---|---|---|---|
| The equal-cards grid | Five to seven pricing or option cards, same size and style, none recommended | Hick's Law, Analysis Paralysis | Three in view, one recommended, the rest behind "Compare all" |
| The feature wall | Each plan with its own long feature list in its own order | Analysis Paralysis, Cognitive Load | Same attributes, same order, short; detail in a comparison table |
| Everything is primary | Several filled buttons or "Popular" badges competing | Von Restorff Effect, Selective Attention | One high-emphasis element per view or group |
| The flat mega-nav | Ten or more top-level links in one ungrouped row | Hick's Law, Chunking | Five or so groups with labels; the rest inside them |
| The tiny target | A 16 to 28 px icon button, close "x", checkbox or text link as the only target | Fitts' Law | A hit area that meets the platform minimum (see numbers below), with space around it |
| The wall of fields | Every field on one screen, optional mixed with required, no groups | Principle of Least Effort, Chunking, Cognitive Load | Ask only what is needed now, group the rest under headings, mark optional |
| The placeholder label | Placeholder text as the only label | Signifiers, Short-Term Memory | A visible label above each field; placeholder only for an example |
| The strict input | Rejecting spaces in a phone or card number, uppercase in an email, trailing whitespace | Postel's Law | Accept, normalize, then validate |
| The silent button | An async action with no pending, success or error state | Feedback, Doherty Threshold | Acknowledge within 400 ms; show pending, then the result |
| The blame-y error | Validation only on submit, a generic message at the top, the form cleared | Feedback, Selective Attention, Peak-End Rule | Message beside the field, saying how to fix it, input kept |
| The twin buttons | Confirm and cancel, or save and delete, styled the same and touching | Stroop Effect, Fitts' Law | Different styles for opposite actions, destructive one separated |
| The mystery icons | Icon-only actions with no labels | Signifiers, Law of Closure | Icon plus text, or text alone; icon-only for true conventions only |
| The hover secret | Actions that appear only on hover, right-click or swipe | Discoverability, Affordances | A visible control for every action |
| The reinvented control | A hand-built select, date picker, checkbox or scrollbar | Jakob's Law, Mental Model | The native or standard component, styled |
| The stepless wizard | A multi-step flow with only "Next" and no sense of length | Goal-Gradient Effect, Zeigarnik Effect | "Step 2 of 4" with named steps and a way back |
| The dead end | A success page that says "Success!", an empty state that says "No items" | Peak-End Rule, Paradox of the Active User | Confirm what happened and offer the next action; give empty states a first step |
| The welcome tour | A multi-slide intro or modal tour before any real use | Paradox of the Active User | Start in the product with one obvious first action and hints in place |
| The uniform gap | One spacing value everywhere, so labels float between fields | Law of Proximity | Less space inside a group than between groups |
| The card soup | Every element in its own bordered box, boxes inside boxes | Law of Common Region, Law of Prägnanz | Group with spacing first; a border only where grouping is unclear |
| The cascade maze | Hover menus three levels deep that close when the pointer drifts | Accot-Zhai Steering Law | Two levels at most, opened on click or with a short delay |
| The distant control | An "Add" button far from where the item appears, a "Save" far from the form | Simon Effect, Mapping, Fitts' Law | Put the control where its effect happens |
| The color-only signal | Status, selection or errors shown by color alone | Von Restorff Effect | Add a label, icon, weight or position as a second cue |
| The memory test | Asking people to carry a code, price or choice from one screen to the next | Short-Term Memory, Tesler's Law | Carry it forward and show it |
| The dark nudge | Pre-checked paid extras, fake countdowns, a decline link styled to be missed | Cognitive Bias | Extras unchecked, real information only, decline as clear as accept |

## Numbers to build to

Published figures. Use them as written and name the source if you quote one.

- **Response:** acknowledge every action within 400 ms (Doherty Threshold). About 0.1 s
  feels instant, about 1 s keeps the train of thought, about 10 s is the limit of
  attention, so show progress and a way to cancel for long work (Jakob Nielsen's
  response-time limits).
- **Touch targets:** at least 44 by 44 pt hit region for buttons on Apple platforms
  (Human Interface Guidelines), at least 48 by 48 dp with 8 dp between targets on Android
  (Google's accessibility guidance).
- **Web targets:** at least 24 by 24 CSS px to meet WCAG 2.2 level AA (success criterion
  2.5.8), and 44 by 44 CSS px for level AAA (2.5.5). On a touch layout build to 44.
- **Contrast:** 4.5:1 for body text and 3:1 for large text (WCAG 1.4.3); 3:1 for the
  boundaries of controls and for meaningful graphics (WCAG 1.4.11).
- **Color:** never the only cue (WCAG 1.4.1).

There is no published maximum for menu items, plans or form fields. "Seven plus or minus
two" (Miller's Law) is about what people can hold in memory, not what may appear on a
screen. Reduce choices because the decision is hard, not to hit a number.

