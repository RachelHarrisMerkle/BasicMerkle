# Medium guide: charts, dashboards and data stories

Pair this guide with `../flows/dashboards-and-tables.md` for the screen structure. If a data-visualisation skill is installed (for example `dataviz` or a brand's data-visualizer), use it for chart types, palettes and the build; this guide supplies the UX decisions around them.

**Brand:** chart colours and rules from `../brand/dataviz.md`, tokens from `../brand/ui.md`. Inside a `.pptx` use the deck palette (`../brand/pptx/brand-guidelines.md`).

## The laws, as chart and dashboard decisions

| Law | What it means for data |
|---|---|
| Pareto Principle | Give the few numbers people check most the top and the most room. A grid of equal tiles hides which metric matters. |
| Selective Attention, Von Restorff | One focal element per chart or panel: the highlighted series, the annotated point. Mute the rest. |
| Cognitive Load, Occam's Razor | Remove gridlines, borders, 3-D, decoration and legends that do no work. Every mark should carry data. |
| Short-Term Memory | Label lines and bars directly. A legend asks people to remember a colour mapping while they read. |
| Law of Prägnanz | Prefer the simplest chart shape that shows the comparison. Do not make people decode a complex form. |
| Law of Proximity, Similarity | Related panels sit together; the same metric looks the same everywhere it appears. |
| Chunking | Group a long table into labelled sections; a dashboard into a few clear regions. |
| Von Restorff against colour-only | Status and series must differ by more than colour: label, icon, pattern or position as a second cue. |
| Cognitive Bias, Campbell's Law | Honest axes (bars start at zero), stated baselines, no cherry-picked periods, no dual axes that imply a correlation. A metric chosen because it looks good is a bias; ask what the number stands for. |
| Feedback, Doherty Threshold | Filters, sorting and refresh respond within a moment; show a loading state; keep a stale-data indicator visible. |
| States | Design empty, loading, error and no-permission states for every panel (`../flows/states.md`). |

## Checks before you hand it over

1. What is the one question this chart or dashboard answers? Is the answer visible in five seconds?
2. Could a reader name the highest and lowest item without reading a legend?
3. Is anything emphasised that should not be?
4. Do the axes and baseline tell the truth?
5. Does every panel have its empty, loading and error state?
