
# Merkle Design Engineer

> This skill is still growing. It currently covers the **motion tokens** (the
> owner of motion across the system) and the **one rule** for authoring
> render-prop component demos in the Merkle Design System (MDS) docs — more
> interactive-build guidance lands over time.

## Motion tokens

Motion is owned by this skill — `ui.md` hands it here. Reach for the
semantic **transition tokens**, never ad-hoc timings. Each is a duration + easing
pair (the durations and easings resolve through the brand layer, so motion stays
on-brand and tunable from one place). Consume them as
`var(--transition-<name>-duration)` and `var(--transition-<name>-easing)`.

| Token | Use it for |
|---|---|
| `transition.default` | The everyday UI transition — hovers, toggles, small state changes (the snappiest). |
| `transition.enter` | Elements appearing — a popover, toast, or panel entering. |
| `transition.exit` | Elements leaving — the same surfaces dismissing. |
| `transition.expand` | A surface growing or revealing — accordion, collapsible, disclosure. |
| `transition.move` | An element changing position — reordering, a sliding indicator. |

Rules:

- **Pair duration with its easing.** Use `transition.enter` (duration *and* easing)
  for an entrance — don't mix `enter` duration with `default` easing.
- **Match the token to the motion's intent** — enter vs exit vs expand vs move — so
  appearance and dismissal feel deliberate, not uniform.
- **Honour `prefers-reduced-motion`**: gate non-essential motion and fall back to an
  instant state change.
- Anything richer (springs, choreographed sequences, gesture-driven motion) is built
  on `motion/react`; keep the timing anchored to these tokens.

## Render-prop children + function props in MDS docs

MDS components wrap [Base UI](https://base-ui.com/react/overview/quick-start) primitives. Several primitives expose **render-prop children** — the idiomatic Base UI API for collection components:

``tsx
<Autocomplete.List>
  {(item) => <Autocomplete.Item key={item} value={item}>{item}</Autocomplete.Item>}
</Autocomplete.List>
``

This is the correct authoring pattern in application code. **It cannot be authored inline in MDX docs pages.** MDX bodies compile as React Server Components under Fumadocs; functions can't be serialised across the server→client boundary, so the static prerender fails with:

``text
Error: Functions cannot be passed directly to Client Components unless you
explicitly expose it by marking it with "use server".
  {children: function children}
             ^^^^^^^^^^^^^^^^^
``

### The pattern: hoist the showcase into a "use client" demo file

Move the showcase JSX into a named function inside a `"use client"` file alongside the parts re-exports. MDX imports the demo by name; the render function lives entirely on the client side and never crosses the boundary.

**Before** (fails build):

``mdx
<ComponentShowcase name="autocomplete">
  <Autocomplete.Root items={FRUITS}>
    …
    <Autocomplete.List>
      {(item) => <Autocomplete.Item value={item}>{item}</Autocomplete.Item>}
    </Autocomplete.List>
    …
  </Autocomplete.Root>
</ComponentShowcase>
``

**After** (builds clean):

`apps/docs/src/components/docs/demos/autocomplete-demo.tsx`:

``tsx
"use client";

import { AutocompleteRoot, AutocompleteList, AutocompleteItem /* etc */ } from "../autocomplete-parts";

export function AutocompleteShowcase() {
  return (
    <AutocompleteRoot items={["Apple", "Banana", "Cherry"]}>
      …
      <AutocompleteList>
        {(item) => (
          <AutocompleteItem key={item as string} value={item}>
            {item as string}
          </AutocompleteItem>
        )}
      </AutocompleteList>
      …
    </AutocompleteRoot>
  );
}
``

`apps/docs/content/docs/primitives/autocomplete.mdx`:

``mdx
import { AutocompleteShowcase } from "@/components/docs/demos/autocomplete-demo";

<ComponentShowcase name="autocomplete">
  <AutocompleteShowcase />
</ComponentShowcase>
``

### When the rule applies

| Inline pattern in MDX | Hoist? |
|---|---|
| `<Combobox.List>{(item) => <Combobox.Item value={item}>{item}</Combobox.Item>}</Combobox.List>` | **Yes** — render-prop child |
| `<Combobox.Value>{(value) => value.map(v => <Chip key={v}>{v}</Chip>)}</Combobox.Value>` | **Yes** — render-prop child |
| `<Button onClick={() => toast.add({ title: "Saved" })}>Save</Button>` | **Yes** — handler closes over state/imports |
| `<Button render={<a href="/foo">Link</a>}>Click</Button>` | No — `render` takes an element here, not a function |
| `<Tooltip.Popup>Plain text</Tooltip.Popup>` | No — serialisable element child |
| `<Select.Root defaultValue="apple">…</Select.Root>` | No — string prop |

### Naming convention

- File: `apps/docs/src/components/docs/demos/<name>-demo.tsx` (one file per component)
- Functions: `<ComponentName><Scenario>Demo` — e.g. `AutocompleteShowcase`, `AutocompleteGroupedDemo`, `ToastSavedDemo`, `ComboboxFruitDemo`
- One demo function per `<ComponentShowcase>` or `<ComponentPreview>` instance in the MDX page
- Always `"use client"` at the top of the file

### Do not work around it by disabling prerender

`export const dynamic = "force-dynamic"` on the catch-all docs route would mask the error but disables static generation for **every** docs page just to paper over an authoring issue on a handful. The hoist-to-demo fix is mechanical, scales, and matches what `combobox-parts.tsx`, `menu-parts.tsx`, and `toast-parts.tsx` in MDS already do.

### Reference example in this repo

`apps/docs/src/components/docs/demos/autocomplete-demo.tsx` is the reference implementation: the `/docs/primitives/autocomplete` page imports its `"use client"` showcase demos from there, keeping the render-prop child off the server boundary.

### Related

This rule originates upstream in `focus-ui-sandbox/.claude/skills/focus-ui-docs/SKILL.md` (section "Render-prop children + function props"). The two skills stay in sync.


## Merkle brand essentials

**Fonts:** Proxima Nova (go-to-market, external, print), Work Sans beta (digital/internal), Geist Mono beta (code/data values only).

**Token scope (BETA):** DESIGN.md and tokens-merkle-theme are beta — internal/prototype/digital only. For merkle.com and external assets, use the existing Merkle brand guidelines.

**Icons — two systems, never interchange:** Phosphor (`@phosphor-icons/react`) for UI affordances; Merkle brand icons (`npx shadcn add @merkle-create/icons-merkle-brand`) for narrative illustration only.

**Logos:** `logo-merkle`, `logo-digital-shelf`, `logo-the-mix`, `logo-xen` — React components, `color="auto"` for theme-aware rendering. No pre-baked clearspace. Use supplied lockups only — don't recolour or rebuild.

**Scope:** Full design system (fonts, tokens, DESIGN.md, MDS) is BETA — internal/prototype/digital use only.


