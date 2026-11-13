# Merkle brand layer

This skill is Merkle-branded by default. Everything it makes (decks, pages, screens, documents, emails, charts) carries Merkle fonts, colour, logos, icons and voice, and the UX decisions are made inside that brand, not instead of it. Only drop the brand if the person says the work is for another brand or is explicitly unbranded.

The brand material in this folder was taken from the Merkle Create plugin and is bundled so this skill works on its own. Merkle owns it and updates it; see "Keeping it current" below. Internal Merkle / Dentsu use.

## Step 1: Pick the brand regime for the output

Merkle has different rules for different outputs. Pick one before choosing any font or colour, and say which in the UX read.

| Output | Regime | Fonts | Read |
|---|---|---|---|
| Digital product, app, prototype, proof of concept, internal tool or site | Merkle Design System (MDS) tokens and `DESIGN.md` (beta, internal and digital only) | **Work Sans** for UI, body and headlines; **Geist Mono** only for code, annotations and data values | `ui.md` |
| External merkle.com, social and marketing assets | Existing Merkle brand guidelines, not the beta palette | **Proxima Nova** | `ui.md` (rules and scope), plus the brand guidelines, which are not bundled: ask for them |
| PowerPoint (`.pptx`) | Legacy Merkle brand and the `Merkle_2025_v2` theme: its own palette, layouts and wordmark rules | **Arial** by default, **Proxima Nova** when the person chooses it and it is available | `pptx/README.md` and `pptx/brand-guidelines.md` |
| Documents and email | Not specified in the bundled sources. Follow the deck regime for look (it is the closest external, non-interface brand surface) | Proxima Nova, with Arial as the safe fallback for outside audiences | Say this is an assumption and ask the person to confirm |
| Charts, dashboards, data stories | Chart colours from the `DESIGN.md` chart palettes for digital work; the deck palette inside a `.pptx` | As the surrounding output | `dataviz.md` |

Font summary: Proxima Nova is the go-to-market font (merkle.com, external materials, presentations). Work Sans and Geist Mono are beta, for digital products, prototypes and internal work only, not yet external or marketing. Web fonts load through `next/font` (the `font-sans` / `font-mono` registry items carry the snippet), never a hand-written `@font-face` or a Google Fonts `<link>`.

## Step 2: Always apply these, whatever the regime

| Concern | Rule | Read |
|---|---|---|
| Words | Merkle voice, protected terms, copy patterns for web, product UI and slides | `copy.md` |
| Accessibility | Contrast, accessible copy, ARIA and keyboard patterns, reduced motion | `accessibility/README.md` and the file it points to for the task |
| Motion and interaction | Only for interactive builds | `motion.md` |
| Logos | Use the official lockups and treatments only. Do not recolour, distort or rebuild them. Add your own clearspace per the brand guidelines. In a deck the wordmark rules in `pptx/brand-guidelines.md` apply | `ui.md` (logos), `pptx/brand-guidelines.md` |
| Icons | Two systems, never interchanged. **Phosphor** for functional UI (buttons, navigation, status, forms, table actions). **Merkle brand icons** for narrative illustration only (hero, empty states, diagrams, marketing modules), digital and web only: not on merkle.com, in PowerPoint or in print | `ui.md` (icons and craft detail 7) |
| Tokens, not values | In interfaces reference semantic tokens, never raw hex, px or shadow values, and never values remembered from memory. Both light and dark must work | `ui.md` |

## How brand and UX fit together

- **Brand decides how it looks and sounds. This skill decides whether people can use it.** Fonts, palette, tokens, logos, icon sets, voice: brand wins.
- **The brand's own rules are UX rules too.** One hero per view, one primary action, spacing on the grid, differentiated button variants, visible focus: these are in `ui.md` and agree with the laws. Use them as the concrete form of the constraints in the UX read.
- **If a brand execution would break a law at the top of the order** (contrast under the published minimum, a target below the platform minimum, a hidden primary action), do not ship it silently. Keep the brand and propose the nearest compliant brand option (a stronger on-token, a larger hit area). Flag the conflict in one line. Order of concern is in `../laws/which-law-wins.md`.
- **Do not mix regimes in one piece of work.** A deck is the deck regime throughout. A prototype is MDS throughout. Do not borrow the beta palette into an external asset or the legacy hex values into a product UI.

## Keeping it current

- `DESIGN.md` is the single source of truth for interface tokens (colour, type, spacing, radius, shadows, components, chart palettes). It is **not bundled** here because it regenerates every release. If a build needs real token values, get it with `npx shadcn add @merkle-create/merkle-design-md` and save it as `references/brand/DESIGN.md`. This skill reads it when present. When it is absent, use token names only, do not invent values, and say tokens were not resolved.
- The Merkle PowerPoint master template (`Merkle_PPT_Template.pptx` or similar) is **not bundled**. Deck rebuilds and from-scratch decks need it. Ask the person to supply it.
- If the person has the Merkle Create plugin or registry access, refresh the files in this folder from it when Merkle publishes a new release. Registry items use names such as `ui-button`, `tokens-merkle-theme`, `font-sans`, `icons-merkle-brand`, `logo-merkle`.
- The bundled files still contain the plugin's original wording. Where they say "this skill" or name another Merkle skill, read that as this brand layer and the sibling file in this folder.
- The whole MDS (fonts, tokens, `DESIGN.md`, components) is beta. Client-facing merkle.com, external marketing and PowerPoint follow the existing brand guidelines and Proxima Nova until Merkle says otherwise.

## Files

```
brand/
  README.md          this router
  ui.md              visual UI rules: tokens, elevation, spacing, radius, finishes, craft details, icons, logos
  copy.md            Merkle voice and copy rules (web, product UI, slides)
  dataviz.md         charts, dashboards, data stories on Merkle tokens
  motion.md          motion and interactivity on Merkle tokens
  accessibility/     README plus contrast, copy, components, motion
  pptx/              README, brand-guidelines (palette, type, layouts, wordmark), approach-a-patch,
                     approach-b-rebuild, slide-patterns (XML helpers)
```
