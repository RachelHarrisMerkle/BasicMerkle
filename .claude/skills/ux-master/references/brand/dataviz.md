
# Merkle Data Visualizer

Use this skill to make a Merkle chart, dashboard, or data story say the right thing
and look the part. It is **usage and selection** — *which* chart, *which* palette,
and the rules that keep colour honest — on top of **`DESIGN.md`** (the spec, which
now carries the resolved chart palettes) and the **`ui-chart`** + recharts system the
charts are built on. It does **not** cover building a new chart type or styling the
page around the chart — see [Hand-offs](#hand-offs).

## Working method

1. **Read the `DESIGN.md` "Chart palettes" section first.** Every chart token —
   `chart-brand-*`, `chart-distinct-*`, `chart-sequential-*`,
   `chart-diverging-semantic-*`, `chart-diverging-brand-*`, `chart-semantic-*`,
   and the chrome tokens — resolves there to its light/dark hex,
   regenerated from the `semantic-charts` tokens each release. Never substitute a
   remembered hex; recalled values go stale.
2. **Pin down the one question** the chart answers. A chart that answers two
   questions answers neither — split it.
3. **Pick the chart type** for that question ([below](#choosing-a-chart-type)).
4. **Pick the palette** for what the colour has to *communicate*
   ([below](#choosing-a-palette)) — not for decoration.
5. **Apply through the token contract** ([below](#the-token-contract)) — set the
   palette on the container, reference `--chart-*`, never hardcode a hex.
6. **Apply the data-story craft** ([below](#data-story-craft)).

`DESIGN.md` is the single source of truth for chart token values — don't read hexes
from anywhere else. The docs add only what the spec can't: **[Styling](https://create.merkle.design/docs/data-visualisation/styling)**
for live swatches and the palette rationale, the **[chart components](https://create.merkle.design/docs/charts/bar-chart)**
for the catalogue with code, and **[Cartographer](https://create.merkle.design/docs/data-visualisation/cartographer)**
for the no-code builder.

## Choosing a chart type

Pick by the question, not by what looks impressive. The chart components render
**recharts** through the Tailwind-free **`ui-chart`** wrapper.

| The question is about… | Reach for | Notes |
|---|---|---|
| Comparing values across categories | **Bar** | Grouped, stacked, or horizontal. Horizontal when labels are long. |
| A value over time, emphasis on level | **Area** | Time series with gradient fills; stack for part-to-whole over time. |
| A value over time, emphasis on rate | **Line** | Multi-series; dash a projection or forecast. |
| Part-to-whole, a few slices | **Pie / Donut** | ≤5 slices; a donut can hold a centre total. Past that, use a bar. |
| Correlation between two measures | **Scatter** | Add a third measure as bubble size. |
| Mixed measures on shared axes | **Composed** | Bars + lines + areas together (e.g. volume bars + a rate line). |
| One entity across many metrics | **Radar** | Comparable, normalised spokes only. |
| Progress toward a target / a gauge | **Radial** | Concentric bars or a 180° gauge. |
| Stage-by-stage drop-off | **Funnel** | Ordered stages; show the conversion between them. |

Exotic types recharts lacks (candlestick, choropleth, sankey) are backlogged — don't
hand-roll an engine; escalate via `the Merkle chart contribution guide (not bundled)`.

## Choosing a palette

Six palette families, each for a different colour job. Pick by what the colour
must communicate. The exact tokens and hex live in `DESIGN.md` → Chart palettes
— the single source of truth; reference them, never a remembered or hand-picked
value.

| Palette | Use it for | `data-chart-palette` |
|---|---|---|
| **Brand / Distinct** | Categorical series. Brand is automatic for 1–5 series; Distinct is automatic for 6–7 and can be explicitly selected. | *(automatic)* / `distinct` |
| **Sequential** | Ordered magnitude, low → high (heatmap, choropleth, density). | `sequential` |
| **Semantic Diverging** | Ordered negative → neutral → positive deviation around a meaningful midpoint. | `semantic-diverging` |
| **Brand Diverging** | Brand-led ordered deviation around a meaningful midpoint. Direct labels and a second encoding are required. | `brand-diverging` |
| **Semantic** | Discrete polarity — gain, no change, loss (P&L, KPI deltas). | *(use the semantic tokens)* |

Two rules hold across every palette:

- **Keep categorical series to seven or fewer.** Brand is never used above five;
  Distinct takes over automatically at six. Past seven, group the long tail into
  "other", or label series directly.
- **Never rely on colour alone.** ~8% of men have a colour-vision deficiency. Pair
  colour with shape, a dashed line, a pattern, or a direct label.

## The token contract

A chart stays on-brand and theme-correct because it reads tokens, never literals.

- **Set the palette once on the container** with `data-chart-palette`. Categorical
  charts automatically use Brand through five series, then Distinct at six or
  more; `distinct` is the explicit categorical override. Don't set `--chart-*`
  on individual marks.
- **Point each series at a slot** in `ChartConfig`: `color: "var(--chart-1)"`,
  `var(--chart-2)`, … The slots resolve to the active palette and theme-flip
  automatically — no per-mode colour code.
- **For a one-off mark colour**, pass a slot explicitly (`<Bar fill="var(--chart-3)" />`).
  Still a token — **never a hardcoded hex.**
- **Chrome reads its own tokens** (`--chart-grid`, `--chart-label`, …); the default
  glass tooltip and legend are already token-styled — use them as-is.
- **Brand Diverging requires direct labels and a second encoding** — position,
  sign, pattern, or shape. It is never a safe colour-only distinction.
- If a chart needs more than seven categorical series, aggregate the tail or
  label it directly rather than relying on repeated colours.

## Data-story craft

The small rules that make a chart read true. They sit on top of the spec.

1. **One question per chart.** State it in the title.
2. **Order with meaning.** Sort categorical bars by value (not alphabetically) unless
   the category has its own order (time, size buckets).
3. **Bars start at zero.** A truncated bar axis lies about proportion. Lines may use a
   focused range when the *change* is the point — say so.
4. **Label the point.** Annotate the value that carries the story rather than making
   the reader decode the axis; direct-label series instead of leaning on a legend
   where you can.
5. **Tabular numerals everywhere numbers align** — axes, data labels, tables — so
   digits stay equal-width and nothing shifts. (A `DESIGN.md` rule; charts are no
   exception.)
6. **Let the data breathe.** Thin the grid, drop chartjunk; the marks carry the
   meaning, the chrome only supports them.
7. **Brand stays a surface, not the data.** On a dark surface the series palette is
   tuned for legibility — don't recolour series to "more blue"; keep brand for the
   card/hero around the chart, per `ui.md`.

## Static vs interactive

- **Interactive** (a React app, dashboard, PWA): compose recharts inside `ui-chart`.
  Install once — `npx shadcn add @merkle-create/ui-chart` — and recharts + the Merkle
  theme come with it; no Tailwind, no per-chart package.
- **Static** (a deck, a doc, a screenshot): build it in
  **[Cartographer](https://create.merkle.design/cartographer)** — the no-code builder —
  and export an image, or copy the generated `ui-chart` code. It renders through the
  same wrapper and palette, so a static export is already on-brand and theme-correct.
- **For a `.pptx` deck**, the chart still follows the legacy Merkle brand, not the beta
  palette — hand the deck itself to `pptx/README.md`.

## Hand-offs

This skill picks the chart and the palette. It hands off:

- **Building a new chart type** (composing recharts, the `ui-chart` wrapper, registry
  wiring) → **`the Merkle chart contribution guide (not bundled)`**.
- **The surface around the chart** (card treatment, spacing, glow, where it sits in
  the layout) → **`ui.md`**.
- **A `.pptx` deck** → **`pptx/README.md`**.
- **Brand universals** (fonts, palette scope, icons, logos) → `README.md`.


## Merkle brand essentials

**Fonts:** Proxima Nova (go-to-market, external, print), Work Sans beta (digital/internal), Geist Mono beta (code/data values — use for chart data labels and tabular figures).

**Token scope (BETA):** DESIGN.md, tokens-merkle-theme, and semantic-charts chart palettes are beta — internal/prototype/digital only. For merkle.com and external assets, use the existing Merkle brand guidelines.

**Icons — two systems, never interchange:** Phosphor (`@phosphor-icons/react`) for UI affordances; Merkle brand icons (`npx shadcn add @merkle-create/icons-merkle-brand`) for narrative illustration only.

**Logos:** `logo-merkle`, `logo-digital-shelf`, `logo-the-mix`, `logo-xen` — React components, `color="auto"` for theme-aware rendering. No pre-baked clearspace. Use supplied lockups only — don't recolour or rebuild.

**Scope:** Full design system (fonts, tokens, DESIGN.md, MDS) is BETA — internal/prototype/digital use only.


