# Merkle Brand Guidelines

> Hex values are the active source of truth for this skill. Token names are listed for
> reference — this skill uses the **legacy Merkle brand** (Proxima Nova / Arial,
> `#040E4B` / `#0391F2`, `Merkle_2025_v2`). It does NOT use MDS tokens, Work Sans, or
> the beta palette.

---

## Colors

### Brand Base Colors

| Token Name | Hex | Usage |
|------------|-----|-------|
| `brand-color-base-primary` | `#040E4B` | Dark backgrounds, primary shapes, headers |
| `brand-color-base-secondary` | `#0391F2` | Highlights, links, bright accents |
| `brand-color-base-tertiary` | `#0328D1` | Active/interactive accents |
| `brand-color-base-neutral-dark` | `#000033` | Darkest background option |
| `brand-color-base-neutral-light` | `#8888A1` | Supporting text, secondary elements |
| `brand-color-gulf-blue` | `#041677` | Supporting dark elements |
| `brand-color-klein` | `#031FA4` | Mid-tone blue accents |
| `brand-color-base-utility-error` | `#DD3038` | Accent only — CTAs, warnings, key callouts |

### Neutral Scale

| Token Name | Hex | Usage |
|------------|-----|-------|
| `theme-color-neutral-1` | `#FFFFFF` | Text on dark backgrounds, clean backgrounds |
| `theme-color-neutral-4` | `#F2F2F4` | Near-white backgrounds |
| `theme-color-neutral-5` | `#E5E5E9` | Light section backgrounds |
| `theme-color-neutral-6` | `#D6D6DF` | Light borders, subtle backgrounds |
| `theme-color-neutral-7` | `#AEAEBC` | Borders, dividers |
| `theme-color-neutral-9` | `#8888A1` | Secondary text |
| `theme-color-neutral-12` | `#000000` | Base dark |

### Theme Role Mapping (for XML edits)

| XML Role | Token Name | Hex |
|----------|------------|-----|
| `dk1` | `theme-color-neutral-1` | `#FFFFFF` *(inverted scheme — dk1 is white)* |
| `lt1` | `theme-color-neutral-12` | `#000000` |
| `accent1` | `brand-color-base-primary` | `#040E4B` |
| `accent2` | `brand-color-base-secondary` | `#0391F2` |
| `accent3` | `brand-color-klein` | `#031FA4` |
| `accent6` | `brand-color-base-utility-error` | `#DD3038` |

### Off-Brand → Brand Color Remaps

These are colors commonly found in decks not built from the Merkle template. The code
remap in `approach-a-patch.md` applies these to user slide content.

> **Note:** `#333333` and `#555555` are intentionally excluded from the code remap —
> they appear as design elements in the Merkle agenda slide template (divider lines and
> row numbers). Remapping them would corrupt correctly-built agenda slides. If a user
> deck contains these as body text or fill colors, remap them manually.

| Off-brand | Token Name | Hex | Notes |
|-----------|------------|-----|-------|
| `#1F2937` | `brand-color-base-primary` | `#040E4B` | Dark slate → Merkle Blue |
| `#0657D3` | `brand-color-base-tertiary` | `#0328D1` | Off-blue → Cobalt |
| `#0B1148` | `brand-color-base-primary` | `#040E4B` | Near-navy → Merkle Blue |
| `#2E4EAB` | `brand-color-klein` | `#031FA4` | Mid-blue → Klein |
| `#E03C31` | `brand-color-base-utility-error` | `#DD3038` | Off-red → Merkle Red |
| `#6B7280` | `brand-color-base-neutral-light` | `#8888A1` | Medium gray → Dark Gray |
| `#888888` | `brand-color-base-neutral-light` | `#8888A1` | Neutral gray → Dark Gray |
| `#D1D5DB` | `theme-color-neutral-6` | `#D6D6DF` | Light gray → Mid Gray Tint |
| `#E8E9EC` | `theme-color-neutral-5` | `#E5E5E9` | Very light gray → Light Gray |
| `#111111` | `brand-color-base-primary` | `#040E4B` | Near-black → Merkle Blue |
| `#364153` | `brand-color-base-primary` | `#040E4B` | Dark slate variant → Merkle Blue |
| `#4A5568` | `brand-color-base-neutral-light` | `#8888A1` | Mid slate → Dark Gray |
| `#60607D` | `brand-color-base-neutral-light` | `#8888A1` | Muted purple-gray → Dark Gray |
| `#AAAAAA` | `brand-color-base-neutral-light` | `#8888A1` | Light gray → Dark Gray |
| `#DDDDE6` | `theme-color-neutral-6` | `#D6D6DF` | Near-mid gray tint → Mid Gray Tint |
| `#E4E4EC` | `theme-color-neutral-5` | `#E5E5E9` | Near-light gray → Light Gray |
| `#EFF2FA` | `theme-color-neutral-4` | `#F2F2F4` | Near-light gray tint → Light Gray Tint |
| `#F2F2F2` | `theme-color-neutral-4` | `#F2F2F4` | Near-white → Light Gray Tint |
| `#F3F4F6` | `theme-color-neutral-4` | `#F2F2F4` | Near-white → Light Gray Tint |
| `#F4F4F7` | `theme-color-neutral-4` | `#F2F2F4` | Near-white → Light Gray Tint |
| `#F5B840` | `brand-color-base-secondary` | `#0391F2` | Off-brand gold/yellow → Sky Blue |

---

## Typography

### Font Families

| Token Name | Value | Usage |
|------------|-------|-------|
| `brand-typography-display-font-family` | `Proxima Nova` | Display, headlines |
| `brand-typography-headline-font-family` | `Proxima Nova` | All headings |
| `brand-typography-paragraph-font-family` | `Proxima Nova` | Body copy |

### Font Selection

Always ask the user to choose a font before proceeding. Present the options and guidance:

> "Which font would you like to use for this presentation?
>
> - **Arial** *(default)* — recommended if this presentation will be shared with people outside of Merkle. No installation required; renders reliably on any device.
> - **Proxima Nova** — closer to the Merkle brand identity. Requires the font to be installed on the recipient's device or embedded in the file.
>
> If you're unsure, Arial is the safer choice for external audiences."

**If the user does not respond or skips the choice → use Arial and notify:**
``
ℹ️  No font selected. Arial has been applied by default.
    If this presentation is for internal use or a brand-critical deliverable,
    re-run and select Proxima Nova (requires font installation or embedding).
``

### Font Availability Check (Proxima Nova only)

If the user selects Proxima Nova, verify availability before applying:

1. **Is Proxima Nova embedded in the uploaded template file?**
   Check `ppt/fonts/` inside the unpacked `.pptx` for `.fntdata` files. If present → use `Proxima Nova`.
2. **Is Proxima Nova installed on the system?**
   ``bash
   python3 -c "import matplotlib.font_manager as fm; print('Proxima Nova' in [f.name for f in fm.fontManager.ttflist])"
   ``
   If `True` → use `Proxima Nova`.
3. **Neither available → fall back to Arial and warn the user:**
   ``
   ⚠️  Proxima Nova was selected but could not be found (not embedded in template,
       not installed on system). Arial has been applied instead.
       To use Proxima Nova, ensure it is installed on your device or embedded in
       the master template file.
   ``

### Type Scale

| Token Name | Size | Weight | Usage |
|------------|------|--------|-------|
| `typography-display-lg` | 24pt | Bold (700) | Slide title |
| `typography-headline-md` | 14pt | Regular (400) | Body / subheadline |
| `typography-eyebrow` | 10pt | Bold (700) | Eyebrow / label — ALL CAPS |
| `typography-paragraph-sm` | 12pt | Regular (400) | Caption / footnote |

**Note on QA rendering:** Proxima Nova is not available in LibreOffice, so visual QA previews will show a substitute font. The font embedding procedure (in the approach files) ensures correct rendering in PowerPoint. Trust the XML, not the preview, for font checks.

---

## Spacing

Base unit: `brand-scale-base-ui` = **4px**

| Token Name | Value | PPT Equivalent |
|------------|-------|----------------|
| `spacing-200` | 8px | Tight internal padding |
| `spacing-300` | 12px | Default element gap |
| `spacing-400` | 16px | Standard section spacing |
| `spacing-800` | 32px | Large margin / slide padding |

---

## Slide Layouts

The Merkle template has 35 layouts. Key ones:

| # | Name | Use For |
|---|------|---------|
| 1 | Title Page | Cover — plain (safe for slides with own bg) |
| 4 | Title Page - Texture 3 | Cover — with built-in dark texture bg |
| 8 | Agenda - Texture | Agenda with dark bg |
| 10 | Agenda Slide 1 | Agenda — clean, no background |
| 13 | Divider Slide 1 | Section break — minimal, no bg image |
| 14 | Divider Slide - Texture, Dark | Section break with dark texture |
| 25 | Title & Body + EYEBROW | Content with eyebrow label |
| 26 | Title & Body + EYEBROW + LINE | Content with eyebrow + divider line |
| 27 | Title & Body | Standard content — plain white |
| 28 | Title & Body 2 Column | Two-column content |
| 29 | Title & Body 3 Column | Three-column content |

### Layout Selection by Approach

| Slide type | Approach A (patch) | Approach B (rebuild) |
|---|---|---|
| Cover / title | layout 1 (plain) | layout 4 (Texture 3) |
| Agenda | layout 10 (clean) | layout 8 (Agenda - Texture) |
| Section divider | layout 13 (minimal) | layout 14 (Divider - Texture, Dark) |
| Standard content | layout 27 | layout 27 |
| Content + eyebrow | layout 26 | layout 26 |
| 2-column | layout 28 | layout 28 |
| 3-column | layout 29 | layout 29 |

Approach A uses plain/structural layouts because the existing slide already has its own background shapes. Approach B can use Texture layouts because slides are built fresh with no conflicting background.

### Layout Rules

- Slide size: **16:9 widescreen** (12192000 × 6858000 EMUs = 33.87cm × 19.05cm)
- Theme: `Merkle_2025_v2`

---

## Visual Identity Rules

| Rule | Requirement |
|------|-------------|
| Font | User's choice: **Arial** (default, external audiences) or **Proxima Nova** (internal/brand-critical, requires availability check) — see Font Selection above |
| Theme | `Merkle_2025_v2` must be installed in every output file |
| Background | Full dark theme — avoid light-background content slides; layout 27 (plain white) is the documented exception |
| Primary accent | `brand-color-base-primary` (`#040E4B`) and `brand-color-base-secondary` (`#0391F2`) only |
| Headlines | Left-aligned — never centered |
| Body copy | Left-aligned — never centered |
| Wordmark | Full `MERKLE` wordmark on title slide only; small `M` mark on all interior slides |
| Eyebrow | ALL CAPS, letter-spaced, `typography-eyebrow` (~10pt bold), top-left |
| Decorative lines under titles | Never — use whitespace and eyebrow labels for hierarchy instead |

---

## Custom Slide Flagging

A slide is **custom** (needs designer review) if:
- Its content does not fit any standard layout (cover, agenda, divider, body, 2-col, 3-col)
- It uses a non-standard visual structure (infographic, chart-heavy, image grid, timeline)
- The copy volume is significantly larger or smaller than the placeholder allows
- It was created manually rather than from a template layout

For every custom slide, add a speaker note:
``
⚠️ DESIGNER REVIEW: Custom layout — verify fit and spacing.
``

---

## Designer Review Summary

Every delivery must end with this summary. If there are no custom slides, state that explicitly.

``
DESIGNER REVIEW SUMMARY
=======================
Approach used: A (Patch) / B (Rebuild)
Total slides: N
Custom slides flagged: N

FLAGGED SLIDES
--------------
Slide [N] — [One-line reason]

ITEMS NOT COVERED BY AUTOMATED PROCESS (manual designer check required)
------------------------------------------------------------------------
• Visual rendering of Proxima Nova — confirm font displays correctly in PowerPoint
• Geometric/photographic background images on Texture layouts — verify they render as expected
• Logo placement and scaling — verify Merkle M mark and wordmark positions
• Image bleed and crop on full-bleed slides — pixel-level alignment must be checked in PowerPoint
• Color accuracy on projected/printed output — hex values are set correctly but calibration may shift
• Slide-to-slide spacing consistency — uniform vertical rhythm should be confirmed by eye
• Eyebrow label presence — confirm every content slide carries the correct EYEBROW label text
• Custom slide content legibility — flagged slides use the content distribution pattern; designer should refine
• Speaker notes reviewed and removed before client delivery — ⚠️ notes are internal use only
``
