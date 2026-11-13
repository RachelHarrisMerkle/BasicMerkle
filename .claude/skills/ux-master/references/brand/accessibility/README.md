
# Merkle Accessibility Advocate

## When to activate this skill

Activate whenever any of these conditions arise — regardless of which other skill is already active:

- **Contrast** — choosing text/background colour pairs, verifying token choices, reviewing designs in light and dark themes
- **Copy** — writing alt text, form labels, error messages, link text, or accessible button/icon names
- **Components** — building interactive components (dialogs, tabs, accordions, menus) and needing ARIA roles, keyboard navigation, or focus management
- **Motion** — adding animation, transitions, or scroll effects to any Merkle surface
- **Audit** — reviewing existing UI for WCAG compliance

This skill layers on top of other Merkle skills; it does not replace them. When `../ui.md` is active and colour contrast is the question, load `contrast.md` and apply it alongside the visual decisions. Same for engineering (../motion.md + `components.md`) and copy (../copy.md + `copy.md`).


## Universal rules — always apply, no reference file needed

These are short enough to hold in context at all times.

1. **Test contrast in both themes.** MDS sets `data-theme="light"` or `"dark"` on `<html>`. A token pair that passes in light can fail in dark. Always check both.

2. **Semantic HTML first, ARIA second.** A `<button>` is more accessible than `<div role="button">`. Use HTML elements for their meaning; add ARIA only where HTML cannot express it.

3. **Never convey meaning through colour alone.** Errors, statuses, and data series must use shape, label, or pattern alongside colour. A red icon is not an error message.

4. **All interactive elements must be keyboard-reachable.** If a mouse user can activate it, a keyboard user must reach it with Tab/arrow keys and trigger it with Enter or Space.

5. **Visible focus is non-negotiable.** Do not suppress `outline` without providing an equivalent focus indicator. MDS focus-visible styles are built into every interactive component — do not override them.

6. **Reduced-motion is a user preference, not an edge case.** Every `motion.*` component and CSS transition must provide a no-movement alternative when `prefers-reduced-motion: reduce` is set.


## Reference map — load only what you need

Load one reference file per task. Each file is focused; loading all four adds context weight without benefit.

| Task at hand | Load this reference |
|---|---|
| Choosing colours, verifying contrast ratios, APCA, MDS token pairs | [`contrast.md`](contrast.md) |
| Alt text, form labels, error messages, link text, icon names | [`copy.md`](copy.md) |
| ARIA roles, keyboard nav, focus management, Base UI component patterns | [`components.md`](components.md) |
| Animation, transitions, prefers-reduced-motion in motion/react | [`motion.md`](motion.md) |


## MDS accessibility foundation

These facts apply across all four reference domains.

**Theming:** All MDS semantic tokens (`--color-on-surface`, `--color-surface-container-*`, `--color-intent-*`) resolve per `data-theme`. Contrast audits must use computed CSS values, not token names — toggle the theme in DevTools and sample actual colours.

**Components:** MDS components are built on Base UI v1.5. Base UI manages the ARIA contract for complex widgets — roles, states, keyboard behaviour, and focus. Do not override Base UI's ARIA management; override its CSS.

**Colour tokens for text:**
- `--color-on-surface` — primary text, designed to pass WCAG AA on all `--color-surface-container-*` values
- `--color-on-surface-subtle` — secondary/decorative text; **verify before using for interactive or informational text**
- `--color-primary-on-brand` — text on `--color-primary-brand` surfaces
- `--color-intent-{success,warning,error,info}-*` — status tones; **verify each pair in both themes**

**Motion:** MDS uses `motion/react` (Framer Motion). Constants: `SPRING = {type:"spring", duration:0.35, bounce:0}`, `SPRING_FAST = {type:"spring", duration:0.25, bounce:0}`. `AnimatePresence` always uses `initial={false}`.


## Merkle brand essentials

**Fonts:** Proxima Nova (go-to-market, external, print), Work Sans beta (digital/internal), Geist Mono beta (code/data values only).

**Token scope (BETA):** DESIGN.md and tokens-merkle-theme are beta — internal/prototype/digital only. For merkle.com and external assets, use the existing Merkle brand guidelines.

**Icons — two systems, never interchange:** Phosphor (`@phosphor-icons/react`) for UI affordances; Merkle brand icons (`npx shadcn add @merkle-create/icons-merkle-brand`) for narrative illustration only.

**Logos:** `logo-merkle`, `logo-digital-shelf`, `logo-the-mix`, `logo-xen` — React components, `color="auto"` for theme-aware rendering. No pre-baked clearspace. Use supplied lockups only — don't recolour or rebuild.

**Scope:** Full design system (fonts, tokens, DESIGN.md, MDS) is BETA — internal/prototype/digital use only.


