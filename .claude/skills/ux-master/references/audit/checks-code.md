# Detection checks for code

Generated from the card files. These are signals you can verify by reading source: markup, styles, components and handlers.
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

- An action exists only behind hover, right-click, long-press, swipe or a keyboard shortcut, with no visible control for it. Look for `:hover`-only reveals, `onContextMenu`, gesture recognizers and key handlers that have no matching button or menu item.
- The primary action of the screen sits inside an overflow menu (`...`, "More", kebab) or below a collapsed section.
- Icon-only buttons with no visible text and no accessible name (`aria-label`, `accessibilityLabel`, `contentDescription`).
- An empty state renders nothing, or only "No items", with no control that starts the first task.
- Navigation that appears only after scrolling or only at one breakpoint.

### Selective Attention (`selective-attention`)

- Important messages rendered in banner-like containers at the top of the page or in a side rail, styled like promotions.
- State changes that happen away from the control that caused them, with no transition, highlight or announcement: a total that updates at the bottom of a long page, a list that reorders silently, an error summary far from the field.
- Several things changing at once after one action.
- More than one element with the strongest visual treatment in a view: several filled primary buttons, several badges, several animated elements.
- Auto-advancing carousels, looping animation or video near the task.
- Toasts or notices that disappear on a short timer and cannot be seen again.
- Live updates with no announcement for assistive technology (`aria-live` or the native equivalent).

### Pareto Principle (`pareto-principle`)

- No visual priority among features: every action, card or tile given equal size and position, with the most-used ones not first.
- The most common task takes more steps than a rare one.
- Defaults that suit a rare case, so most people have to change them.
- Dashboards showing every available metric at equal weight.
- Settings and options ordered alphabetically or by implementation order where frequency of use would serve better.
- In a review: a long flat list of findings with no order of importance.

### Serial Position Effect (`serial-position-effect`)

- The most important or most used item sits in the middle of a navigation list, tab bar or button group. Check the order of nav children and tab definitions.
- Low-value items (legal links, rarely used tools) placed first or last in a primary bar.
- The primary action in the middle of a row of actions, not at the end the platform expects.
- The key message of a page in the middle of long content, with neither the opening nor the closing section stating it.
- Onboarding or carousel sequences where the most important slide is neither first nor last.

### Von Restorff Effect (`von-restorff-effect`)

- No distinct primary action: every button in a view uses the same variant, or the main action is styled as secondary.
- Too many: more than one high-emphasis button, badge or highlight competing in one view. Count the elements using the strongest style.
- A set of options (plans, cards, tiles) where the recommended one has the same styles as the rest.
- Difference carried by color only: status, selection, errors or the recommended item marked with a hue change and nothing else. WCAG 2.2 success criterion 1.4.1 requires that color is not the only visual means of conveying information.
- Weak difference: emphasis that does not meet the 3:1 contrast WCAG 2.2 asks of user interface components (success criterion 1.4.11), or differs from its neighbors only slightly.
- Attention-seeking animation with no reduced-motion alternative (`prefers-reduced-motion` or the platform setting).
- Emphasis on the wrong thing: the loudest element is a promotion, a secondary action or decoration.

## Lens 2: Choice and load

How much does the screen ask people to decide, read, remember and do?

### Cognitive Load (`cognitive-load`)

- One view that mixes several unrelated tasks: more than one form, or several primary actions, rendered together.
- Forms where every field is shown at once, required and optional mixed, with no sections or steps.
- Text blocks used where a short label would do: long instructions above a form, paragraphs inside buttons or table cells.
- Many distinct visual treatments in one view: count the different font sizes, weights, colors and button styles in the styles for that screen. A high count with no system behind it is extraneous load.
- The interface asks people to work something out that the system already knows: totals, time zones, remaining characters, which plan they are on.
- Inconsistent placement of the same control across similar screens.
- Auto-playing media, animation loops or banners that compete with the task.

### Chunking (`chunking`)

- Long runs of sibling elements with no grouping: many inputs in a row with no `<fieldset>`, section heading or step; many nav items with no group labels or separators; many table columns with no grouping.
- Long strings rendered or requested unformatted: a 16-digit card number, an IBAN, a license key or a one-time code as one unbroken run.
- Text walls: paragraphs with no headings, lists written as sentences.
- Headings that skip levels or are all the same level, so structure is flat.
- Lists longer than a screen with no categories, filtering or search.

### Analysis Paralysis (`analysis-paralysis`)

- A "choose one" set rendered with equal weight and no default, no recommendation and no way to narrow it.
- Options described with different attributes or in a different order, so they cannot be compared row by row: plan cards whose feature lists do not line up.
- Long option lists with no search, filter or sort.
- Differences between options hidden behind tooltips or separate pages.
- Options that differ by one or two small details presented as separate, equal choices.
- No way to see selected items together when comparing across pages.

### Short-Term Memory (`short-term-memory`)

- Information shown on one screen that must be typed or chosen on another: a code, an ID, a price, a selected option. Check whether earlier choices are passed forward and displayed.
- Placeholder used as the only label or the only format hint, so it disappears while typing.
- Filters, sort order or search terms applied but not shown, or lost on navigation.
- Comparison that requires switching between pages or tabs with no side-by-side view or pinned selection.
- Multi-step flows with no summary of earlier answers and no way to review before submit.
- Validation rules shown only after failure, so people must remember them for the retry. Passwords are the usual case.
- Visited links styled the same as unvisited ones in a long list of destinations; no breadcrumb or "you are here" cue in deep navigation.
- One-time codes that cannot be pasted or auto-filled (`autocomplete="one-time-code"` missing on the web).

### Hick's Law (`hicks-law`)

- Count sibling options at each decision point: plan cards, top-level nav items, buttons in one toolbar or dialog, radio options, tabs. No research gives a hard cap. As a working heuristic, treat more than about 5 to 7 equal-weight, ungrouped options as a prompt to look for grouping, a default or a recommendation.
- Several primary-styled actions in one view (more than one filled, high-emphasis button competing).
- Choice sets with no default selection and no recommended option.
- Dialogs with three or more actions of equal weight.
- First-run screens that expose every feature or setting at once.
- Long flat menus with no groups, separators or search.
- Over-simplification: hamburger or "More" menus hiding primary navigation on wide screens, or icon-only choices with no labels.

### Miller's Law (`millers-law`)

- Instructions that list several steps in advance and then hide them while the steps are carried out.
- Codes, IDs or values people must carry from one view to another (see Short-Term Memory for the checks).
- Long unformatted strings to read or type.
- Long flat sets of anything (fields, options, columns) with no grouping. The fix is grouping, not deletion.
- Misuse to flag in a review: content or navigation arbitrarily cut to seven items or fewer, with needed items hidden as a result.

### Occam's Razor (`occams-razor`)

- Elements with no function for the screen's task: decorative icons, repeated headings, badges, dividers, illustrations, duplicate links to the same place.
- Options and settings with no evidence of use, or two controls that do the same thing.
- Extra steps: confirmation pages that confirm nothing, interstitial screens, a "review" step for a single field.
- Fields that are not needed to complete the task (see Principle of Least Effort).
- Custom components where a standard element would do the same job.
- Wrapper elements, modals within modals, tabs with one tab.
- Copy that restates the label or the obvious ("Enter your email in the email field below").

### Parkinson's Law (`parkinsons-law`)

- Form fields missing `autocomplete` attributes (name, email, tel, address parts, `cc-number`, `one-time-code`) or the native equivalents, so browsers and password managers cannot fill them.
- Known information asked for again: details the account already holds, a billing address when "same as shipping" would do, a country that could be inferred and offered as the default.
- No sensible defaults on selects, dates or quantities.
- Paste disabled on any field.
- No saved progress: a long form that loses everything on refresh, back or timeout.
- Open text areas with no guidance on expected length where a short answer is wanted.
- Flows that promise a duration ("Takes 2 minutes") and contain far more than that.

### Tesler's Law (`teslers-law`)

- The person does work the system could do: calculating totals, converting units or time zones, typing data the system already has, choosing a card type that the number reveals, picking a country that could be inferred and offered.
- No defaults where a sensible one exists.
- Format rules imposed on input instead of parsing (see Postel's Law).
- Dependent fields that do not update one another: choosing a country does not adjust the state or postal code field.
- Technical choices exposed with no guidance: region, encoding, protocol, cache or sync mode shown to people who cannot judge them.
- Raw system errors passed straight through to the screen.
- The opposite failure: essential controls hidden or removed so the screen looks simple, leaving people unable to predict or steer the result. A single "Go" button with no visible options or summary.
- Automation with no visibility and no override.

### The Principle of Least Effort (`principle-of-least-effort`)

- Fields that are not needed to complete the task at this point: phone number on a newsletter sign-up, company size on a trial, date of birth with no stated reason. For each field ask what breaks if it is removed or asked later.
- Optional fields mixed in with required ones and not marked.
- Duplicate entry: "Confirm email", "Confirm password" with no show-password toggle, address typed twice.
- Account creation required before the person has received any value, where a guest path could exist.
- Long content shown in full where a summary with "Show more" would serve most readers.
- Explanatory paragraphs where an example, default value or inline preview would show the same thing.
- More steps or clicks for the common path than for a rare one.
- The easiest visible path leads to the wrong outcome: the most prominent button is not the one most people need.

## Lens 3: Visual structure

Does the look of the screen show what belongs together and what comes first, and is it easy to read?

### Aesthetic-Usability Effect (`aesthetic-usability-effect`)

- Inconsistent visual system: many one-off values for spacing, font size, radius, shadow and color instead of a small set of tokens or variables. Count the distinct values in the styles for the screen.
- Misalignment: sibling elements with different paddings, margins or baselines for no reason.
- Low-contrast text. WCAG 2.2 asks for a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text (success criterion 1.4.3).
- Unstyled or default states: raw browser controls beside custom ones, missing hover, focus and disabled styles.
- Images stretched, cropped badly or missing dimensions so the layout jumps while loading.
- The reverse problem: heavy decoration (gradients, shadows, animation on every element) on a screen whose functional findings are still open.

### Law of Common Region (`law-of-common-region`)

- A control rendered outside the container of the content it acts on: a card's action button placed after the card's closing tag, a form's submit outside the form's panel, a table's bulk-action bar detached from the table.
- Unrelated content sharing one container: two separate tasks in one card or panel.
- Nested containers several levels deep (a card in a card in a panel), each with its own border or background, so boundaries stop meaning anything.
- Every element given its own bordered box, so no grouping is expressed at all.
- List or table rows with no row boundary (no divider, zebra background or spacing), making it unclear which values belong to which row.
- Sections of a long page with no visual boundary and no heading.

### Law of Proximity (`law-of-proximity`)

- Uniform spacing everywhere: one `gap`, margin or padding value used both inside groups and between them. Compare the space between a label and its field with the space between that field and the next label; the first must be clearly smaller.
- A label, helper text or error message closer to the neighboring field than to its own.
- A heading with equal space above and below, so it does not attach to the section it introduces. It should sit closer to what follows.
- Related actions separated (Save in the header, Cancel in the footer) or unrelated actions adjacent (Delete touching Save).
- A control far from the content it affects.
- Icon and label of one item spaced as widely as two separate items.

### Law of Prägnanz (`law-of-pragnanz`)

- No consistent grid or alignment: siblings with different widths, offsets or start edges for no content reason. Look for many one-off widths and margins.
- More alignment axes than needed: left-aligned, centered and right-aligned blocks mixed in one section.
- Cards or tiles in one row with different heights, paddings or internal structure.
- Decorative shapes, dividers, borders and backgrounds that do not mark a real boundary.
- Icons drawn with heavy detail at small sizes, or mixed icon styles (outline and filled, different stroke weights) in one set.
- Charts with unnecessary effects, dense gridlines or many near-identical series colors.

### Law of Similarity (`law-of-similarity`)

- One role, several styles: primary buttons with different colors, sizes or radii across a screen or flow; links that are underlined in one place and not in another. Search the styles for near-duplicate button and link rules.
- Several roles, one style: primary, secondary and destructive actions sharing a class or variant; interactive text styled the same as body text; headings the same size as body.
- Color used for more than one meaning: the brand color on both links and non-interactive headings, red for both errors and a sale badge.
- Status indicators (success, warning, error) that differ only slightly, or the same status shown differently in two places.
- Icons from mixed sets or at mixed weights within one group.
- Similar-looking items that behave differently: some cards in a grid open on click and others do not.

### Law of Uniform Connectedness (`law-of-uniform-connectedness`)

- Steps in a flow rendered as separate items with no connecting line or bar, so they read as unrelated badges instead of a sequence.
- A tab that is not visually joined to its panel: a gap or border between the active tab and the content it controls.
- Nested or threaded content (replies, sub-tasks, tree nodes) indented with no guide line, where depth is hard to follow.
- Paired inputs (start and end date, minimum and maximum) rendered as two unrelated fields with no joining label or connector.
- A dropdown, popover or tooltip that opens detached from its trigger with no pointer or alignment.
- Connections that are wrong: a divider or line that visually joins unrelated items, or a continuous bar that links actions belonging to different objects.

### Law of Closure (`law-of-closure`)

- Horizontal scrollers and carousels where the visible items fit the container exactly, so nothing is cut off and nothing shows that more exists. No partial item, arrow, dots or count.
- A page section that ends at the bottom of the first screen with a full-width band or large spacing, so the page looks finished. This is the illusion of completeness.
- Truncated text or lists with no ellipsis, "Show more" or count ("+3 more"), or truncation with no way to see the full content.
- Icon-only controls built from abstract or heavily simplified shapes with no label (see Signifiers).
- Skeleton placeholders whose shapes do not resemble the content that will load, so the page jumps when it arrives.
- Progress rings or bars that look complete before the task is done.

### Law of Continuity (`law-of-continuity`)

- Siblings that should align but do not: labels and fields with different left edges, buttons at different baselines, cards with different top offsets. Look for one-off margins, paddings and transforms on individual siblings.
- Form fields laid out in an irregular grid (some full width, some half, some thirds) so there is no single line to follow downward.
- Multi-column forms where the reading order zigzags and tab order does not match the visual order.
- No visual break between sections: one unbroken column for unrelated groups.
- A break where none is meant: an indent, divider or offset in the middle of a single group.
- Visual order that differs from source or focus order (`order`, absolute positioning, `tabindex` greater than zero), so the eye follows one path and the keyboard another.

## Lens 4: Targets and movement

Can people hit and reach the controls without slips?

### Fitts' Law (`fitts-law`)

- Interactive elements whose hit area is below a published minimum. The floors, strictest last:
  - WCAG 2.2 success criterion 2.5.8 (level AA): at least 24 by 24 CSS pixels. The exceptions include a smaller target with enough space around it (a 24 pixel circle centered on it does not touch another target), a link inside a sentence, and an unmodified browser control.
  - Apple Human Interface Guidelines: a button needs a hit region of at least 44 by 44 points (60 by 60 on visionOS). Apple lists 28 by 28 points as the minimum control size on iOS and iPadOS, and 28 by 28 default with 20 by 20 minimum on macOS.
  - WCAG 2.2 success criterion 2.5.5 (level AAA): at least 44 by 44 CSS pixels.
  - Google's Android accessibility guidance: at least 48 by 48 dp, with 8 dp or more between targets.
- Work out the real size: width, height, `min-width`, `min-height`, padding, line height and icon size together. An icon of 16 to 24 pixels with no padding is the usual failure. Check close buttons, icon buttons, checkboxes, radio buttons, pagination, chips and links in dense lists.
- Adjacent targets with no gap (`gap: 0`, touching borders), especially a destructive action touching a safe one.
- Text links as the only way to trigger a primary action.
- Form labels not connected to their control (`<label for>` or wrapping label missing), so clicking the label does nothing and the target is only the small box.
- The primary action placed far from the last input: at the top of a long form, or in the opposite corner.

### Simon Effect (`simon-effect`)

- An "Add" control placed at the opposite end from where new items appear: new rows append at the bottom but the add button is at the top right, or the reverse, with no scroll to the new item.
- Row actions detached from their rows: actions for a selected item in a distant toolbar with no visible link to the row.
- Direction conflicts: "Back" or "Previous" on the right in a left-to-right layout, "Next" on the left, a carousel whose left arrow advances.
- In right-to-left locales, direction not mirrored (`dir="rtl"` unsupported, hard-coded `left` and `right` instead of logical properties).
- Feedback that appears far from the action: an error at the top of the page for a field at the bottom, a toast in the opposite corner from the control.
- Controls that change position between states: a button that swaps places with another after a click, or "Confirm" appearing where "Cancel" was.

### Accot-Zhai Steering Law (`accot-zhai-steering-law`)

- Nested menus three or more levels deep.
- Submenus opened on `:hover` or `mouseenter` and closed immediately on `mouseleave`, with no delay and no tolerance for diagonal movement toward the submenu.
- Menu rows that are narrow in the steering direction: short row height in a long vertical menu the pointer must travel down before moving sideways.
- Sliders with a thin track and small thumb, or a wide value range on a short track so tiny movements matter. No text input or stepper offered as an alternative.
- Drag and drop as the only way to reorder or move items, with small drop zones or long distances and no keyboard or button alternative.
- Hover-revealed controls that disappear when the pointer leaves a thin strip.
- Custom thin scrollbars as the only way to scroll a region.

## Lens 5: Signals and feedback

Do controls say what they do, and does the system say what happened?

### Affordances (`affordances`)

- Click or tap handlers on generic containers (`<div onClick>`, a tappable `View` or `Text`) with no button or link semantics and no pressed, hover or focus style.
- Elements styled as buttons (filled background, border radius, pointer cursor) that have no handler, or are disabled with no visual difference from enabled.
- Links styled as plain body text: no underline and the same color as surrounding text.
- Inputs with no border, background or underline, so they look like static text.
- Draggable items with no handle and no cursor or style change.
- `cursor: pointer` on things that do nothing, or default cursor on things that act.

### Signifiers (`signifiers`)

- Icon-only controls with no visible label and no tooltip. Check every `<button>` or tappable whose only child is an icon or SVG.
- Form fields with no persistent label. The placeholder is used as the label, so it disappears on input. Look for inputs with `placeholder` and no associated `<label>`, `aria-label` or visible text.
- Expandable regions (accordion, disclosure, dropdown) with no chevron, plus sign or state change between open and closed.
- Scrollable containers with hidden scrollbars and no cut-off content, fade or arrow to show there is more.
- Required and optional fields that are not marked.
- Links whose text is "click here" or "learn more" with nothing saying where they lead.

### Feedback (`feedback`)

- Async handlers (`fetch`, `await`, server actions, mutations, network calls) with no pending state: the trigger is not disabled, shows no spinner or label change, and nothing else on screen changes while the request runs.
- No error branch. `catch` blocks that are empty, only log, or set no user-visible state. Promises with no rejection handling.
- No success state: after a successful save or submit, nothing visible changes.
- Destructive or irreversible actions that complete with no confirmation of what was done and no undo.
- Missing interaction states in styles: no `:hover`, `:active`, `:focus-visible`, `[disabled]` or pressed style on interactive elements.
- Current location not indicated: navigation with no active or `aria-current` state.
- Form errors that say only "Invalid" or "Error", or appear far from the field they refer to.

### Mapping (`mapping`)

- Controls placed in a different container from their effect with nothing linking them: a filter bar that changes a list several sections away, a "Save" button in a header that saves a form far below.
- Controls ordered differently from the things they control (three columns, but their three toggles listed in another order).
- Sliders or steppers whose value decreases to the right or upward, or whose plus and minus are reversed.
- Toggles where the label describes the off state, or where it is unclear whether the label names the current state or the action ("Notifications off").
- Carousels or pagers whose previous and next arrows are on the unexpected sides or move content in the opposite direction.
- Keyboard arrow handling that moves selection against the visual layout.

### Doherty Threshold (`doherty-threshold`)

- Network or async calls with no immediate visual change: no pending state, disabled state, spinner, skeleton or optimistic update on the trigger or the affected region.
- Whole-page blocking loaders where part of the page could render first.
- Search, filter or validation that runs on every keystroke against a server with no local feedback, or that waits for a full round trip before showing anything.
- Animations and transitions on direct feedback longer than 400 ms: check `transition-duration`, `animation-duration` and spring settings on hover, press, open and close.
- Artificial delays (`setTimeout`, `sleep`, `delay`) before feedback. A deliberate delay on the result is acceptable only if input is acknowledged first.
- Long operations with an indeterminate spinner only. Jakob Nielsen's widely used response-time limits (about 0.1 second feels instant, about 1 second keeps the train of thought, about 10 seconds is the limit of attention) suggest showing progress and a way to cancel for anything near 10 seconds.
- Large unoptimized assets or render-blocking work on the first screen, when a running page is available to measure.

### Stroop Effect (`stroop-effect`)

- A destructive action given the primary or success style: "Delete" on the brand's filled button, or in green.
- A safe default (Cancel, Keep) styled as the dangerous one, or the two given identical styles.
- Semantic color contradicting content: an error in green, a success in red, a warning in the brand's neutral color, a "free" label in the error color.
- Icon and label disagreeing: a check mark on "Cancel", a right arrow on "Back", a plus icon on a button that opens a menu, a trash icon on "Archive".
- Toggle state contradictions: the "on" position gray and "off" colored, or a label that reads "Disable" while the switch shows enabled.
- Double negatives in labels and checkboxes ("Uncheck to not receive emails").
- Disabled-looking controls that are active, or the reverse.

## Lens 6: Expectations

Does it work the way people already expect?

### Conceptual Model (`conceptual-model`)

- One concept with several names across the product (Project, Workspace, Board used for the same thing), or one name used for two different things. Search the user-facing strings.
- Internal or technical terms in the interface: IDs, table names, enum values, status codes shown as labels.
- Metaphors used inconsistently: a "trash" that deletes immediately, an "archive" that cannot be reopened, a "draft" that other people can already see.
- Actions whose scope is unclear from the label: "Delete" (this item, or everything selected, or the whole account?), "Share" (with whom?), "Sync" (which direction?).
- State that is saved automatically in some places and needs an explicit save in others, with no cue telling them apart.

### Cognitive Dissonance (`cognitive-dissonance`)

- A control's label and its handler disagree: "Save" that also publishes, "Next" that submits, "Cancel" that discards without asking, "Back" that leaves the flow.
- Links that open new windows, start downloads or trigger actions with no cue.
- A control that looks like one kind and behaves like another: a checkbox that navigates, a link that deletes, tabs that submit a form.
- Changing one setting silently resets or changes another.
- The same gesture or shortcut doing different things on similar screens.
- Toggles that take effect immediately in some places and need "Save" in others.

### Mental Model (`mental-model`)

- Core patterns rebuilt in an unusual way: a cart that is not called a cart or is not reachable from every page, search that does not run on Enter, a logo that does not link home, a modal that does not close on Escape.
- Navigation organized by the company's internal structure (team names, database entities) instead of the tasks people come to do.
- Terms taken from the codebase or the business in user-facing strings.
- A redesign that moves or renames core actions with no transition help: no pointer from the old place, no notice, no way back.
- Standard gestures or keys (swipe back, pull to refresh, Tab, Escape, Cmd or Ctrl plus Z) overridden or ignored.

### Jakob's Law (`jakobs-law`)

- Custom replacements for standard controls: hand-built selects, checkboxes, date pickers, scrollbars, text inputs or video controls that drop expected behavior (keyboard support, focus, native pickers on mobile).
- Broken web conventions: logo not linking home, links that are not `<a>` elements (so open in new tab and copy link fail), buttons that are not buttons, back button broken by client-side state, no visible focus, scroll hijacking, right-click disabled.
- Standard placement ignored: search not in the header, account and cart not top right in a left-to-right store, primary navigation in an unusual place, form submit not at the end of the form.
- Standard meaning ignored: an icon with a strong conventional meaning (magnifier, gear, trash, house, heart) used for something else.
- Platform patterns mixed: an iOS-style back gesture pattern in an Android app, or web patterns inside a native app.
- A redesign with no transition: old URLs break, moved features have no pointer, no option to switch back for a while.

### Paradox of the Active User (`paradox-of-the-active-user`)

- A blocking tutorial on first run: a multi-slide carousel, a full-screen overlay or a forced product tour before any real use. Look for onboarding modals triggered on first load with several steps.
- Instructions placed before the interface they describe: paragraphs above a form or tool. Their presence usually means the interface does not explain itself.
- Help that exists only outside the product: links to docs with no inline hint, example or tooltip at the point of need.
- Tours that cannot be skipped or reopened.
- Empty states with no example content, starting action or hint about what belongs there.
- Error messages that assume knowledge only the documentation gives.
- Features that work only if something was configured first, with nothing prompting the setup at the moment it is needed.

## Lens 7: Input and recovery

Does it accept what people give it and help them recover from mistakes?

### Constraints (`constraints`)

- Free-text inputs for values that come from a small known set (country, plan, state, yes or no). A select, radio group or segmented control would remove invalid input.
- Date, time, quantity or range inputs with no `min`, `max` or `step`, where the valid range is known.
- Wrong input type or keyboard: `type="text"` for email, number, phone or URL; no `inputmode` or `autocomplete`; no equivalent keyboard type on native.
- Submit or next actions that are enabled when required input is missing and then fail, or actions that should be unavailable in the current state but are still clickable.
- Steps in a flow that can be opened out of order when order matters.
- Irreversible actions (delete, send, pay) with no confirmation step and no undo.
- Validation rules that exist only on the server, so the first sign of a problem is a round trip.

### Postel's Law (`postels-law`)

- Validation that rejects input the system could normalize: spaces or dashes in phone and card numbers, leading or trailing whitespace, uppercase in emails, a missing `https://` on a URL, a currency symbol or thousands separator in an amount, lowercase postal codes.
- Strict `pattern` attributes or regular expressions on names, phone numbers, addresses or postal codes. Names in particular must accept apostrophes, hyphens, spaces, non-Latin letters and single-word names.
- Date fields that demand one typed format with no picker and no tolerance for alternatives.
- `maxlength` that silently cuts off pasted content.
- Search with exact-match only: no trimming, no case folding, no tolerance for a small typo.
- File inputs that reject common formats or large files with no explanation and no stated limit.
- Layouts that break with long names, long words, translated strings or zoomed text: fixed widths and heights on text containers, truncation with no way to read the full value.
- On the sending side: the same data shown in different formats on different screens (dates, currency, units).

## Lens 8: Progress and endings

Can people see how far they are, and does the task end well?

### Flow (`flow`)

- Modal dialogs, confirmations or upsells that interrupt a routine, reversible action.
- Blocking spinners for operations that could run in the background or update optimistically.
- Focus that is lost or misplaced after an action: after adding an item, focus is not in the next input; after closing a dialog, focus does not return to the trigger.
- No keyboard path through a repeated task, or a path that needs the mouse at one step.
- Automatic interruptions during input: surveys, tooltips, chat prompts, session-expiry dialogs with no warning.
- Work lost on error, navigation or timeout because there is no autosave or draft.
- Difficulty that does not adapt: experts forced through beginner steps every time, or beginners dropped into an expert view.

### Goal-Gradient Effect (`goal-gradient-effect`)

- A flow with more than one step and no step indicator: no "Step 2 of 4", progress bar or checklist. Look for step state (an index, a route per step, a wizard component) with nothing rendering it.
- Progress indicators that do not match reality: a fixed-width bar, a total step count that changes midway, a bar that reaches the end before the last step.
- Long flows where the hardest step comes last with no warning.
- Setup checklists that start at zero when the person has already done something that counts.
- No estimate of remaining effort for long tasks ("About 2 minutes left", "3 questions to go").
- The final step looks the same as the others, so nothing signals "last one".

### Peak-End Rule (`peak-end-rule`)

- Success and confirmation states that are missing or bare: a redirect to the home page with no message, or a page that says only "Success".
- Confirmation with no next step and no record: no summary of what was done, no receipt or reference, no "what happens now".
- Error handling at the highest-stakes steps (payment, submit, upload) that loses the person's input or gives no way forward.
- Flows that end in a dead end: no link onward, no way back to where the person was.
- The last step of a flow is the heaviest: a surprise extra form, a forced survey or an upsell just before or after completion.
- Cancellation and off-boarding flows built to obstruct.

### Zeigarnik Effect (`zeigarnik-effect`)

- Multi-session tasks with no saved state: drafts not kept, a half-completed form reset on return, a cart emptied on logout.
- Incomplete items that look the same as complete ones in a list: no "Draft", "Incomplete" or "2 of 5" marker.
- No resume point: returning to a flow starts at step one instead of where the person stopped.
- Setup or onboarding with tasks remaining and nothing showing them: no checklist, count or progress.
- Content cut off with no cue that more exists (see Law of Closure and Signifiers).
- Overuse: permanent badges, repeated reminders or "complete your profile" banners for optional tasks, with no way to dismiss them.

## Lens 9: Honesty

Is the design helping people reach their own goal, or steering them?

### Cognitive Bias (`cognitive-bias`)

- Pre-checked boxes that add cost, share data or subscribe people to something. Look for `checked`, `defaultChecked` or a default `true` on optional paid or consent options.
- Countdown timers or "only 2 left" messages that are not backed by real data: a timer that resets on reload, a stock count that is a constant.
- Decline options written to shame ("No thanks, I don't want to save money").
- Accept and decline given unequal weight for a consent or cancellation choice: one a filled button, the other small low-contrast text.
- A default that benefits the business and is hard to change later.
- Prices shown without required fees until the final step.

### Campbell's Law (`campbells-law`)

- Interface choices whose only purpose is a metric: a mandatory account before any value is delivered, notifications on by default, an "Are you sure?" chain on cancel or unsubscribe, autoplay to raise watch time, infinite scroll with no end point where people came for a specific item.
- Engagement mechanics (streaks, badges, counters) attached to actions that do not help the person.
- Analytics events that measure activity (clicks, time on page) with nothing that measures whether the task was completed.
- An experiment with one success metric and no guardrail metric, such as conversion with no refund, complaint or retention measure.
- In a spec or pull request: a change justified by a single number with no user evidence.
