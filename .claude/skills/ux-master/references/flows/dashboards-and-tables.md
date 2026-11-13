# Playbook: dashboards and data tables

Overview screens, reports, lists of records and data tables. These are usually tools for
repeat use, so the balance shifts toward density, speed and scanning.

## Laws that matter most

1. **Pareto Principle.** A few numbers and a few actions account for most of the use.
   They get the prime positions.
2. **Selective Attention.** People scan a dashboard for what changed or needs action.
   Everything else should stay quiet.
3. **Cognitive Load and Law of Prägnanz.** Dense is fine. Disordered is not. A clear grid
   and a consistent structure let people read many values quickly.
4. **Law of Proximity, Common Region and Similarity.** Grouping tells people which
   numbers belong together and which labels belong to which values.
5. **Short-Term Memory.** Comparing values that are not on screen together is hard. Keep
   what is compared side by side, and keep headers and filters in view.
6. **Doherty Threshold and Feedback.** Sorting, filtering and loading data need an
   immediate response.
7. **Campbell's Law.** A dashboard decides what a team pays attention to. Choose what it
   shows with care.

## Build rules: dashboards

1. **Start from the questions.** List the two or three questions people open this screen
   to answer. Those answers go top left in left-to-right layouts, largest.
2. **Rank, do not tile.** Avoid a grid of equal cards for unequal metrics. Give the few
   that matter size and position, and group the rest under headings.
3. **Say what the number means.** Every figure has a label, a unit, a period and
   something to compare it with: a previous period, a target or a trend.
4. **Make exceptions stand out and nothing else.** Reserve strong color and badges for
   values that need action. Pair color with an icon or text.
5. **Lay it out on a grid.** Align tiles on shared edges. Keep one style for charts of
   the same kind, and the same color for the same series everywhere.
6. **Link each number to its detail.** A figure that prompts a question lets people click
   through to the records behind it.
7. **Show freshness.** Say when the data was last updated. Load sections independently,
   with placeholders shaped like the content.
8. **Measure outcomes, not only activity.** Next to counts of clicks and sessions, show
   whether people reached their goal.

## Build rules: tables and lists

9. **Choose the columns people use.** Most used first, the identifying column on the
   left. Offer a way to show or hide the rest.
10. **Align for scanning.** Text left, numbers right with the same number of decimals,
    units in the header. Use tabular figures if the typeface has them.
11. **Keep rows readable.** Enough row height or a divider or alternating background to
    follow a row across a wide table (Law of Common Region).
12. **Keep context in view.** Sticky header row, a sticky first column on wide tables,
    and applied filters and sort shown as visible chips or markers.
13. **Make row actions local.** Actions for a row sit in that row, visible or behind a
    labeled "More" button, not only on hover. Bulk actions appear near the table when
    rows are selected, with a count (Simon Effect, Mapping).
14. **Respond at once.** Sorting and filtering show a pending state within 400 ms and
    keep the old rows visible until the new ones arrive.
15. **Handle volume.** Paginate or virtualize long lists, show the total, and provide
    search and filters once the list is longer than a screen or two.
16. **Truncate with care.** Never truncate numbers, amounts or dates. Truncated text has
    a way to be read in full.
17. **Design the empty, loading, error and no-results states.** A table with no rows says
    why and offers the next action. See `states.md`.
18. **Size targets for the device.** Compact rows are acceptable on pointer-driven
    desktop tools down to 24 by 24 CSS px targets (WCAG 2.2 AA). On touch, use the
    platform minimums.

## Checks

| Check | Law |
|---|---|
| Can you name the questions this screen answers, and are their answers the most prominent things on it? | Pareto Principle, Selective Attention |
| Are all tiles the same size regardless of importance? | Pareto Principle, Von Restorff Effect |
| Does every figure have a label, unit, period and comparison? | Conceptual Model, Cognitive Load |
| Is strong color used only for values that need attention, with a second cue? | Selective Attention, Von Restorff Effect |
| Do tiles and charts sit on a shared grid with one consistent style? | Law of Prägnanz, Law of Similarity |
| Is it clear which label belongs to which value? | Law of Proximity |
| Are numbers right-aligned with consistent decimals? | Law of Continuity |
| Do the header row, filters and sort state stay visible while scrolling? | Short-Term Memory |
| Are row actions in the row and reachable without hover? | Simon Effect, Discoverability |
| Do sort and filter respond at once with a pending state? | Doherty Threshold, Feedback |
| Is there search, filtering or pagination for long lists, with a total count? | Hick's Law, Principle of Least Effort |
| Are empty, loading, error and no-results states designed? | Feedback |
| Does the dashboard include a measure of outcome, not only activity? | Campbell's Law |
| Is the last-updated time shown? | Feedback |

## Mistakes this screen invites

Everything is primary (twelve equal tiles), the card soup, the hover secret (row
actions), the color-only signal (status), the distant control (bulk actions far from the
table), the silent button (filters with no response), the memory test (filters applied
but not shown).

## When laws conflict here

- **Density against Cognitive Load.** For daily-use tools, density wins if it is ordered:
  aligned, grouped and consistent. Remove decoration before you remove data.
- **Target size against density.** On pointer-driven desktop tools compact wins, down to
  the WCAG 2.2 AA floor. On touch, target size wins.
- **Show everything against focus.** Show what answers the screen's questions. Make the
  rest reachable (Selective Attention over the wish to display every metric).
- **Miller's Law against long tables.** It does not apply. People read a table, they do
  not memorize it. Help them scan it.

## Research that settles what the laws cannot

Which metrics and columns people use: a contextual inquiry, watching people work with
the current screen, and usage data on which columns are sorted and filtered.
