
# Merkle UI Designer

Use this skill when making visual decisions for a Merkle UI — layout, hierarchy,
component selection, and token application. It is a thin set of execution rules
that sit on top of **`DESIGN.md`** (the spec) and the **MDS React components**.

## Working method

1. **Always read `DESIGN.md` first — it installs with this skill.** It's a registry
   dependency, so `npx shadcn add @merkle-create/skill-ui-designer` pulls it in, and
   it's the **single source of truth** for every token. Values live in its
   frontmatter (`colors`, `darkColors`, `typography`, `spacing`, `rounded`,
   `stroke-width`, `shadows`, `components`); per-token usage in its **Token
   reference** section; chart colour in **Chart palettes**; and the rationale, dos
   and don'ts, and the elevation/radius/spacing usage maps in the prose body
   (**Depth & finishes**, **Shapes**, **Layout**). Match a token to the job by its
   description, then reference it as `var(--token)`. (Motion/transition tokens live
   in `motion.md`.)
2. **Never substitute remembered values.** `DESIGN.md` regenerates from Tokens
   Studio on every release — recalled values go stale.
3. **Prefer MDS components.** If `@merkle-create/mds-react` provides the component,
   use it rather than rebuilding; it already encodes these rules. When composing
   new components, follow the MDS composition and customization rules (compose from
   MDS parts and customise through tokens/variants — see the MDS docs) rather than
   forking or hard-coding.
4. **Apply the execution rules below** as the judgment calls the spec can't encode.

## Execution rules

1. **Reference semantic tokens, never raw values.** Use the semantic-web tokens for
   every visual decision — `color.*`, `spacing.*`, `radius.*`, `shadow.*`,
   `stroke-width.*`, `typography.*`, `opacity.*`, `z-index.*`, `transition.*`. Never
   inline a raw hex, px, or shadow value, even one you read from the spec.
2. **Both light and dark are first-class.** Semantic colour tokens resolve through
   the theme layer, which defines a light and a dark value for each. Design with the
   tokens so both modes work; never hard-code a value that only holds in one mode.
   Use `color.onSurface.inverted` where a colour must keep contrast across a mode swap.
3. **Elevation = `surface-body` fill + shadow + z-index, progressing linearly.**
   Floating/elevated surfaces (resting cards and inputs, popovers, modals, drawers,
   toasts) use `color.surface.body` as their fill, the matching elevation shadow
   (resting **cards** use the theme-aware `shadow.card` — see Craft details; the
   pure-neutral ramp covers the rest — `shadow.neutral.low` for resting inputs →
   `.mid` for dropdowns/popovers/hover cards → `.high` for modals/drawers/overlays),
   and the right `z-index.*` step (`raised` → `floatingMid`/`floatingHigh` → `modal`/`overlay`/`toast`).
   Progress levels linearly — never skip. Shadows are pure-neutral (no coloured
   shadows; a `shadow.primary` set exists for prominent CTAs — use sparingly).
   **Don't add a shadow to a surface already differentiated by container colour**
   (`color.surface.container.low`/`.mid`/`.high`) — the colour contrast already
   implies containment, and doubling up is visual noise. Use the container ramp to
   separate nested areas by colour; reserve shadow for surfaces that actually float.
4. **Pair every fill with its on-token.** Text and icons use `color.onSurface` /
   `color.onSurface.subtle` on neutral surfaces. On a brand or intent fill, use the
   matching on-token (`color.primary.onBrand`, `color.intent.onError`, …); on a
   tinted container, use the `on*Container` token (`color.primary.onContainer`,
   `color.intent.onErrorContainer`, …). Don't mix a fill with a foreground from a
   different family. Watch contrast: never place `color.onSurface.subtle` on
   `color.surface.container.high` — it fails WCAG AA in light mode; use a
   higher-emphasis foreground.
5. **Brand colour roles: primary, secondary, tertiary.** Each exposes `brand`
   (+ `hover`), `container`, `onBrand`, and `onContainer`. Use `primary` for the key
   brand emphasis and main actions, `secondary` and `tertiary` for lower-priority
   brand surfaces and actions. Tertiary is simply lower-priority brand — it is not a
   reserved or special-purpose colour.
6. **Intent colours are semantic and used as a set.** For status and feedback use the
   intent families — `color.intent.{error|warning|success|info}` (solid, with its
   `on*` text) or `color.intent.{…}Container` (tint background, with its
   `on*Container` text). Use an intent colour only to signal that state; never
   decoratively.
7. **Differentiate actions by button variant; stay consistent.** Don't repeat the
   exact same button style for competing actions in a key interaction. Distinguish
   primary vs secondary (vs tertiary) actions using distinct button variants and
   styles (e.g. solid, stroke/outline, lighter/ghost), and keep that mapping
   consistent across the whole experience.
8. **Spacing on the 4px grid.** Every spacing value comes from the `spacing.*`
   scale (4px base unit, `spacing.050`–`spacing.950`). No arbitrary values (7px,
   13px, 18px) — they break the grid. `spacing.100` (4px) is **inset-only** (icon
   padding, tight insets); don't use it as a component-level margin.
9. **Radius by element role.** Use the `radius.*` scale per its intent: `none`
   (tables, technical UI), `smallElements` (chips, badges, inputs), `default`
   (buttons, cards, modals), `largeElements` (banners, hero cards, bottom sheets),
   `full` (pills, avatars, toggles). No improvised radii; never round a single
   corner (except tooltip notches); never use `full` on buttons wider than ~120px
   (use `default`).
10. **Borders, focus, and selection.** Use `color.border.subtle` / `.medium` /
    `.heavy` for borders, and `color.border.focusOutline` with `stroke-width.focused`
    for focus rings; `stroke-width.selected` for selected states. Always provide a
    visible focus state.
11. **Motion uses the transition tokens.** When motion is needed, reach for
    `transition.default` / `enter` / `exit` / `expand` / `move` rather than ad-hoc
    timings — these tokens and richer interactive/behavioural work are owned by
    `motion.md`; reach for it for anything beyond a basic transition.
12. **Typography from the scale.** Use the `typography.*` steps (`display` →
    `headline` → `paragraph`, plus `button`, `link`, `eyebrow`, `legal`, `code`) —
    never improvise intermediate sizes. Work Sans for UI text with `paragraph-md`
    as the floor for standard UI copy; render `eyebrow` UPPERCASE; never weight 900
    on body copy; `code` (Geist Mono) only for code, data values, and monospaced
    contexts.


## The MDS aesthetic

Merkle interfaces read **calm, structured, and confident** — mostly neutral
surfaces, brand colour used sparingly for emphasis, generous spacing on the grid,
and depth that comes from elevation rather than ornament. **Build by composing MDS
components** (`Card` surfaces, `Button`, `Badge`, `Toolbar`, `Tabs`, …) and styling
only through tokens; the components already carry the structure, so your work is
hierarchy and restraint. Make one thing the hero per view — brand gradient/glow,
larger type — and let everything else recede.

## Building signature surfaces

How the Merkle look is composed: not bespoke CSS, but **MDS-native finishes deployed
with restraint**. The gradients, frost, and glows are token-driven inside the
components — your decision is *when* to reach for each, and keeping to the **one hero
per view**. The canonical, in-context reference (every technique below, composed and
shown in both themes) is **[create.merkle.design/reference](https://create.merkle.design/reference)** — design against it.

1. **Finishes pick how a surface is filled.** `Card`/`Sidebar`/`Toolbar` take a
   `finish`: **`solid`** (the neutral default), **`glass`** (frosted translucency over
   content or imagery), **`brand`** (a theme-independent gradient — saturated in both
   modes; it recolours its own title/description on-brand, so no manual on-brand
   overrides). **`CardGlow`** / **`Sidebar.Glow`** add a soft corner brand wash on a
   neutral surface — brand presence at low volume, no gradient fill.
2. **The one hero is a finish, not a colour.** Exactly one `finish="brand"` surface
   **or** one glow carries a view; everything around it stays neutral (`solid`,
   container ramp). Two brand fills competing is the fastest way to read generic.
3. **Cascading opacity over a brand wash.** When neutral surfaces sit on an ambient
   brand gradient, step their opacity to build depth without borders: the surface
   **nearest the wash** drops to a lower opacity (`muted`) so the gradient reads
   through, and adds an elevation shadow to lift; surfaces **further out** stay more
   opaque (`strong`) and recede. Depth comes from opacity + elevation, never a stroke.
4. **Ambient background-gradient recipe.** A region can sit on a subtle brand gradient
   — roughly **~28% brand, radial from the bottom-right** — so the hero and glows read
   against a quietly branded bed rather than flat neutral. Keep it ambient: it's the
   stage, not the focal point.
5. **Glass over imagery.** For a caption over a photo or render, float a `finish="glass"`
   `Card` over a full-bleed image bed and **pin the context `data-theme="dark"`** so
   the frost and `on-surface` text stay legible whatever the surrounding site theme.
6. **Brand belongs in the hairline, not the glyph.** A non-text rule is exactly where
   one stroke of brand fits: `Separator finish="primary"` between bare-surface stats,
   for instance. (This is the dark-surface rule from Craft detail 6 in the positive: a
   brand divider carries no information, so it stays brand; text and icons stay neutral.)
7. **The featured register is for the focal control.** Where a single choice *is* the
   hero, use the emphasized brand register: `Sidebar` `finish="frost"` (glass over a
   deep stage) + `Sidebar.Glow`, or `finish="brand"` (the gradient rail); and
   `ToggleGroup` / `OptionCardGroup` `variant="featured"` (the pressed segment takes the
   brand gradient + glow). Everywhere else, `variant="primary"` is the everyday register
   — featured is the exception, not the default.
8. **The dense metadata register.** For tight panels and toolbars: `Badge size="xs"`
   is an uppercase micro-tag for status/category chips; `Field labelVariant="eyebrow"`
   renders a form label as the same tracked uppercase overline, so labels read as
   section markers.

## Craft details

The small, high-leverage details that separate a considered Merkle UI from a
generic one. They sit on top of the token rules above and introduce no new values.

1. **Concentric border radius.** Nested rounded elements must share a centre, or
   the corners look misaligned: outer radius = inner radius + the inset between
   them. A `radius.default` (8px) card with `spacing.300` (12px) padding gives an
   inner rounded element a smaller radius so the curves stay concentric. Never put
   the same radius on a parent and the child it insets.
2. **Shadows over borders for depth.** A surface that floats reads better with a
   layered elevation than a hard 1px line — and a hairline becomes a visible seam on
   a gradient or image. Resting cards use the theme-aware **`shadow.card`**
   elevation (consumed as `--theme-shadow-card` today; moves to the semantic
   `--shadow-card` once Studio's composite export is fixed): a ring + soft lift in
   light, a subtle white ring in dark, so cards separate cleanly on any background
   and in both themes. Reserve real borders (`color.border.*`) for separation
   **inside** dense UI — dividers, table rules, list separators — not for card edges.
3. **Crisp text.** Set `-webkit-font-smoothing: antialiased` (and
   `-moz-osx-font-smoothing: grayscale`) at the app root so Work Sans renders sharp,
   especially light-on-dark. MDS shells already do this — preserve it when you build
   a new one.
4. **Tabular numbers.** Any number that updates, aligns in a column, or sits in a
   metric / table / price uses `font-variant-numeric: tabular-nums` so digit width
   stays constant and the layout doesn't shift as values change. This is for
   proportional Work Sans — not a reason to switch to `code` (Geist Mono), which
   stays reserved for code and data values.
5. **Optical over geometric alignment.** Trust the eye over the maths: a play
   triangle, an arrow in a round button, or an icon beside a label is often
   geometrically centred yet looks off, and needs a small manual nudge (padding, or
   fixing the SVG) to read as centred. Align optically, not by formula.
6. **Brand colour is a surface, never information, on dark.** On a dark surface
   `primary-brand` (and the triad) belongs only on *non-informational* brand
   surfaces — fills, gradient panels, glows/washes. **Anything that carries
   information stays neutral — text *and* icons alike.** An icon is visual
   information, like text, not an accent; a saturated-blue glyph on dark drops
   contrast exactly the way blue text does. So keep eyebrows, labels, section
   indices, links, **and interface-icon glyphs** neutral (`on-surface` /
   `on-surface-subtle`) on dark. To tie information to the brand, put it on a
   `primary-brand` fill with `primary-on-brand` (a filled button, badge, or
   icon-button) rather than colouring the glyph or text itself:
   ``css
   /* ✗ blue information on dark — muddy, low-contrast */
   .eyebrow      { color: var(--color-primary-brand); }
   .feature-icon { color: var(--color-primary-brand); }
   /* ✓ neutral information; brand carried by the fill underneath */
   .eyebrow      { color: var(--color-on-surface-subtle); }
   .feature-icon { color: var(--color-on-surface); }
   .send-button  { background: var(--color-primary-brand); color: var(--color-primary-on-brand); }
   ``
   On a light surface brand-blue text/icons can read as an accent, but defaulting to
   neutral keeps brand to the one hero per view.
7. **Brand icons are oversized content, never boxed.** The brand icon set
   (`icons-merkle-brand`) showcases content — it is *not* an interface-icon set for
   buttons, rows, or controls (use Phosphor for those). Show brand icons standalone,
   directly on the surface, never in a filled tile or ring (the box washes them out
   and caps the size). Size each as a **fixed multiple of the type it sits with —
   ~2×** the caption/label — by tying the dimension to the type token, so the
   relationship is reproducible and scales with the type:
   ``css
   .brand-icon { /* ~2× the paragraph-lg caption below it */
     inline-size: calc(var(--typography-paragraph-lg-font-size) * 2);
     block-size:  calc(var(--typography-paragraph-lg-font-size) * 2);
   }
   ``
   Let the light/reversed variant swap by `[data-theme]` so the icon stays legible
   on the bare surface.

> **Motion lives elsewhere.** Hover/press feedback, enter/exit, staggering, and any
> timing belong to **`motion.md`** — keep this skill to the static
> aesthetic. (At the token level, motion still uses `transition.*`.)

These principles are adapted from the open design-engineering work behind
**make-interfaces-feel-better** (jakub.kr) and Vercel's **web-design-guidelines**;
we'll evolve our own set as the system matures.


## Merkle brand essentials

**Fonts:** Proxima Nova (go-to-market, external, print), Work Sans beta (digital/internal), Geist Mono beta (code/data values only). Web: `npx shadcn add @merkle-create/font-sans` for the `next/font` snippet.

**Token scope (BETA):** DESIGN.md and tokens-merkle-theme are beta — internal/prototype/digital only. For merkle.com and external assets, use the existing Merkle brand guidelines.

**Icons — two systems, never interchange:** Phosphor (`@phosphor-icons/react`, import named: `import { House } from "@phosphor-icons/react"`) for UI affordances; Merkle brand icons (`npx shadcn add @merkle-create/icons-merkle-brand`) for narrative illustration only.

**Logos:** `logo-merkle`, `logo-digital-shelf`, `logo-the-mix`, `logo-xen` — React components, `color="auto"` for theme-aware rendering. No pre-baked clearspace. Use supplied lockups only — don't recolour or rebuild.

**Scope:** Full design system (fonts, tokens, DESIGN.md, MDS) is BETA — internal/prototype/digital use only.


