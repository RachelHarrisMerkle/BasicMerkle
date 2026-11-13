# Detection checks for screenshots and design files

Generated from the card files. These are signals you can verify by looking: a screenshot, a running page or a design file.
Read the whole file once before you sweep.

- Work through the lenses in order.
- A signal is a place to look, not a verdict. Report it only if it would cost the
  person something on this screen.
- Numbers with a named source (WCAG, Apple, Google, a study) are published figures.
  Any other number is a working heuristic. Say which when you cite one.
- The file for each card
  (`../laws/<card>.md`) adds the example, the conflict rules and the origin.

## Lens 1: Focus

Is there one clear thing to do here, and does the screen lead the eye to it?

### Discoverability (`discoverability`)

- Ask "what can I do here?" and try to answer from the pixels alone in five seconds. If the main action is not among the first things you notice, flag it.
- No element is visually dominant, or several are equally dominant.
- Rows or cards that turn out to be clickable but look like static content.
- Icons with no labels where the meaning is not a near-universal convention (search, close, home, back are safe; most others are not).

### Selective Attention (`selective-attention`)

- Where does the eye land first, second and third? If the first is not the most important thing for the task, flag it.
- Critical information in a colored box that resembles an ad or cookie banner.
- Multiple high-contrast, saturated or moving elements in one view.
- Before and after frames of an interaction: can you spot what changed within a second?

### Pareto Principle (`pareto-principle`)

- Identify the one or two things most people come to this screen to do. Are they the most prominent and the quickest to reach?
- Grids of equal tiles where usage is clearly unequal.
- Rare or advanced options sitting in prime positions.

### Serial Position Effect (`serial-position-effect`)

- For each horizontal or vertical series of five or fewer peers: what is first, what is last, and are those the items that matter most?
- Bottom tab bars on mobile: are the two edge positions and the center used for the most important destinations?
- Long pages: does the last screenful repeat the main action?

### Von Restorff Effect (`von-restorff-effect`)

- Convert to grayscale in your head. Does the important element still stand out?
- Count the loud elements. There should be one per view or per group.
- Check what the loudest element is. It should be the thing the person came to do.

## Lens 2: Choice and load

How much does the screen ask people to decide, read, remember and do?

### Cognitive Load (`cognitive-load`)

- Squint at the screen. If no structure survives (no clear groups, no order of importance), load is high.
- Count the things that ask for a decision or an input in one view.
- Decorative elements, icons or illustrations that carry no information next to content that does.
- Instructions that have to be read before the screen can be used.

### Chunking (`chunking`)

- Count the distinct groups you can see without reading. If the answer is "one", the content is not chunked.
- Whitespace between groups is the same as whitespace within groups.
- Long numbers shown without spacing.
- Sections with no headings.

### Analysis Paralysis (`analysis-paralysis`)

- For any set of choices: is one recommended, and can you see why?
- Lay two options side by side. Can you list their differences in a few seconds without reading everything?
- More than a handful of near-identical cards in a grid.

### Short-Term Memory (`short-term-memory`)

- For each input, ask "where does the person get this value from?" If the answer is another screen, flag it.
- Steps in a flow that do not show what was chosen earlier.
- Active filters with no visible chips or summary.
- Password rules or format requirements that are not visible while typing.

### Hick's Law (`hicks-law`)

- At each point where the person must choose, count the choices and ask which one the design suggests.
- Rows of identical cards or buttons with nothing marked as the usual choice.
- Menus that fill the screen.

### Miller's Law (`millers-law`)

- Anything the person must remember to complete the task.
- Ungrouped runs of similar items.
- An audit or brief that cites "seven" as the reason to remove needed items.

### Occam's Razor (`occams-razor`)

- For each element ask "what would break if this were removed?" If the answer is nothing, flag it as a candidate.
- Two elements that say or do the same thing.
- Decoration competing with content.

### Parkinson's Law (`parkinsons-law`)

- Estimate the time to complete the screen for a first-time visitor. Compare with what the entry point promised.
- Fields the product could have filled in.
- Free-text boxes with no hint of how much to write.

### Tesler's Law (`teslers-law`)

- For each field and choice ask "could the product know or work this out?"
- Instructions that tell people how to format or calculate something.
- A very clean screen whose result people could not predict before pressing the button.

### The Principle of Least Effort (`principle-of-least-effort`)

- Count the inputs. For each one, name the reason it is needed now.
- Count the steps on the main path.
- Text that explains what could be shown.

## Lens 3: Visual structure

Does the look of the screen show what belongs together and what comes first, and is it easy to read?

### Aesthetic-Usability Effect (`aesthetic-usability-effect`)

- Uneven spacing, elements that nearly align, mixed corner radii, more than two or three type sizes with no clear scale.
- Text that is hard to read against its background. WCAG 2.2 asks for a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text (1.4.3). From an image the ratio is an estimate, so say so.
- A screen that looks finished but has open findings in other lenses. Report those first and note that polish may be masking them.

### Law of Common Region (`law-of-common-region`)

- Trace each visible boundary and list what is inside. Is everything inside related, and is anything related left outside?
- Boxes within boxes.
- Buttons floating between two cards so it is unclear which they belong to.

### Law of Proximity (`law-of-proximity`)

- Blur your eyes or view at thumbnail size and count the clumps. The clumps should match the logical groups.
- Ambiguous labels: one that sits midway between two fields.
- Evenly spaced lists of mixed content where groups should exist.

### Law of Prägnanz (`law-of-pragnanz`)

- Reduce the screen to boxes in your head. Is there a simple arrangement (columns, rows, a grid), or do the boxes scatter?
- Count the vertical lines that left edges fall on. Fewer is simpler.
- Icons that need study to recognize.

### Law of Similarity (`law-of-similarity`)

- Group elements by appearance. Does each visual group map to one function?
- Group elements by function. Does each function have one appearance?
- Body text and links that cannot be told apart without hovering.

### Law of Uniform Connectedness (`law-of-uniform-connectedness`)

- Sequences that are not drawn as sequences.
- Lines, arrows or shared bands: for each, check that what it joins is related.
- Floating menus or panels with no visible link to what opened them.

### Law of Closure (`law-of-closure`)

- At the bottom and right edges of each scrollable area: is anything cut off to show continuation?
- Icons that need a second look.
- A first screen that looks like a finished page.

### Law of Continuity (`law-of-continuity`)

- Draw a line down the left edge of the content. Count how many elements sit off it without a reason.
- Follow the natural reading path. Does it pass through the important things in the right order?
- Places where a new section starts with no visible break.

## Lens 4: Targets and movement

Can people hit and reach the controls without slips?

### Fitts' Law (`fitts-law`)

- Measure the smallest interactive elements against the minimum for the platform: a 44 by 44 point hit region for buttons on Apple platforms (Human Interface Guidelines), 48 by 48 dp with 8 dp between targets on Android (Google's accessibility guidance), and on the web 24 by 24 CSS pixels for WCAG 2.2 level AA (2.5.8) or 44 by 44 for level AAA (2.5.5). From a screenshot, estimate from known sizes and mark the figure as an estimate.
- Tightly packed icon rows.
- A primary button that is smaller than secondary elements around it.
- On mobile layouts, primary actions at the very top of a tall screen, the hardest place for a thumb to reach.

### Simon Effect (`simon-effect`)

- For each action, mark where the result will appear. A long distance between the two is a finding.
- Left and right placement of backward and forward controls.
- Consecutive screens of a flow: does the primary button stay in the same place?

### Accot-Zhai Steering Law (`accot-zhai-steering-law`)

- Trace the pointer path for each menu, slider and drag action. Mark any long, narrow corridor.
- Menus that cascade more than two levels.
- Sliders used for precise values with no numeric field beside them.

## Lens 5: Signals and feedback

Do controls say what they do, and does the system say what happened?

### Affordances (`affordances`)

- Cover the labels. Can you still tell which things are pressable, which are editable and which are static?
- Badges, pills or tags that share the exact shape and color of real buttons.
- Flat text that is the only way to trigger an action.
- Disabled controls that look the same as enabled ones, or enabled ones that look washed out.

### Signifiers (`signifiers`)

- Any icon whose meaning you cannot name with confidence without hovering.
- Fields that look empty and unlabeled once filled.
- A row of items that ends exactly at the container edge, hiding that it scrolls.
- Chevrons, arrows or carets that suggest an interaction the element does not have.

### Feedback (`feedback`)

- Buttons with only one visual state in the design file (no pressed, loading, disabled or focus variant).
- No loading, empty, error or success version of the screen exists anywhere in the file.
- Selected items, the active tab or the current step look the same as unselected ones.
- Error messages that do not say what went wrong or what to do next.

### Mapping (`mapping`)

- For each control, draw an imaginary line to what it changes. Long lines, crossing lines or lines to off-screen elements are findings.
- A grid of items with controls laid out in a different order or orientation.
- Toggles with ambiguous state: can you tell on from off without clicking?

### Doherty Threshold (`doherty-threshold`)

- No loading, skeleton or in-progress variant exists for a screen or component that depends on data.
- Buttons with no pressed or loading state in the design file.
- Long processes with no progress indicator or step count.

### Stroop Effect (`stroop-effect`)

- For each control, list what its color, icon, label and position each suggest. Flag any disagreement.
- Pairs of opposite actions that look the same.
- Red or green used on elements that are neither errors nor successes.

## Lens 6: Expectations

Does it work the way people already expect?

### Conceptual Model (`conceptual-model`)

- Read only the navigation labels and headings. Can you describe what the product is and what its main objects are?
- Two screens that show the same kind of object with different names or different layouts.
- Icons or metaphors that promise behavior the product does not have.

### Cognitive Dissonance (`cognitive-dissonance`)

- For each labeled control, write down what you expect to happen. Compare with the prototype links or the spec.
- Elements that borrow a familiar look (a search box, a tab bar, a shopping cart icon) for something else.
- A step whose title promises one thing and whose content asks for another.

### Mental Model (`mental-model`)

- Compare the screen with the two or three most-used products of the same kind. List every structural difference and ask what the difference buys.
- Labels a newcomer would not recognize.
- A familiar-looking layout with familiar elements in unfamiliar positions.

### Jakob's Law (`jakobs-law`)

- Name the category of product, then list what its best-known examples all do. Check each against the screen.
- Familiar controls in unfamiliar places.
- Controls that look custom where a standard one would work.

### Paradox of the Active User (`paradox-of-the-active-user`)

- Imagine all instructions were deleted. Could a newcomer still complete the main task?
- Count the words a person is expected to read before they can act.
- Overlays, coach marks and tours on first load.

## Lens 7: Input and recovery

Does it accept what people give it and help them recover from mistakes?

### Constraints (`constraints`)

- Open text boxes for things with a fixed set of answers.
- No visible limits on ranges: sliders with no end labels, date fields with no hint of the allowed period.
- A destructive button sitting right beside the primary button with the same emphasis.
- Later steps of a flow look available when earlier ones are incomplete.

### Postel's Law (`postels-law`)

- Format instructions that do the system's work ("Enter numbers only, no spaces").
- Fields sized for one expected length.
- Designs shown only with short, tidy sample data.

## Lens 8: Progress and endings

Can people see how far they are, and does the task end well?

### Flow (`flow`)

- Walk the main repeated task. Count the points where the person must stop, wait, confirm or look elsewhere.
- Dialogs layered over a working surface for routine actions.
- No sign of saved state, so people have to stop and check.

### Goal-Gradient Effect (`goal-gradient-effect`)

- For any flow of two or more screens: can you tell from any one screen where you are and how much is left?
- Progress bars with no labels or steps.
- A flow whose last screen does not look like an ending.

### Peak-End Rule (`peak-end-rule`)

- Find the last screen of each flow. Does it confirm what happened, give something useful (a receipt, a next step) and close cleanly?
- Find the error states for the highest-stakes steps. Do they keep the person's work and offer a way forward?
- A final screen that looks unfinished compared with the rest.

### Zeigarnik Effect (`zeigarnik-effect`)

- Any list of the person's own items: can you tell finished from unfinished at a glance?
- After setup: is there a visible account of what is still to do?
- Red badges or nags on things the person never started.

## Lens 9: Honesty

Is the design helping people reach their own goal, or steering them?

### Cognitive Bias (`cognitive-bias`)

- Any place where the choice the business prefers is visually louder than the alternative for a consent, privacy, cancellation or payment decision.
- Urgency, scarcity or social proof messages with no visible source.
- Crossed-out "original" prices with no stated basis.

### Campbell's Law (`campbells-law`)

- Elements that serve the business's dashboard more than the person's task.
- Friction placed on exits (cancel, unsubscribe, delete account) and removed from entries.
- A design rationale that cites one metric only.
