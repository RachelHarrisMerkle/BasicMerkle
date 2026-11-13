# Contrast — Merkle Accessibility Advocate

## WCAG 2.x AA thresholds (minimum for all Merkle digital outputs)

| Text type | Minimum ratio | Rule of thumb |
|---|---|---|
| Normal text (< 18pt regular / < 14pt bold) | **4.5 : 1** | Body copy, labels, small UI text |
| Large text (≥ 18pt regular / ≥ 14pt bold) | **3 : 1** | Display headings, large CTAs |
| UI components (input borders, focus rings, icons) | **3 : 1** | Against adjacent colour |
| Decorative content | No requirement | Only if removing it conveys no information |

18pt ≈ 24px; 14pt bold ≈ 18.67px bold. When in doubt, treat text as normal and apply 4.5:1.

**AA exceptions Merkle does not grant:**
- *Disabled/inactive states* — WCAG permits exemption, but MDS token-driven disabled states should still reach ≥ 3:1 to remain legible
- *Logotypes* — WCAG permits exemption, but Merkle brand colours are designed to pass, so no exemption is needed

---

## APCA / WCAG 3 perceptual contrast (supplementary)

APCA is more accurate than WCAG 2.x ratios for screen typography. Use it for borderline calls and advanced work.

**APCA Lc thresholds (absolute values):**

| Use | Minimum Lc | Approx WCAG equivalent |
|---|---|---|
| Body / running text | Lc 75 | ~4.5:1 |
| Large text (24px+) | Lc 60 | ~3:1 |
| Large bold text (18.67px+) | Lc 45 | ~3:1 |
| Placeholder, non-informational | Lc 30 | decorative floor |

APCA is polarity-aware: dark-on-light and light-on-dark produce different Lc values for the same visual weight. Always check both directions when creating a theme-responsive pair.

**Tool:** https://www.myndex.com/APCA/

---

## MDS token pairs — contrast audit map

Check each pair in **both** `[data-theme="light"]` and `[data-theme="dark"]`.

``js
// Toggle in DevTools console
document.documentElement.setAttribute('data-theme', 'dark')
document.documentElement.setAttribute('data-theme', 'light')
``

| Foreground token | Background token | Expectation | Notes |
|---|---|---|---|
| `--color-on-surface` | `--color-surface-container-low` | ✅ Passes AA | Designed to pass — primary text |
| `--color-on-surface` | `--color-surface-container-mid` | ✅ Passes AA | |
| `--color-on-surface` | `--color-surface-container-high` | ✅ Passes AA | |
| `--color-on-surface-subtle` | `--color-surface-container-*` | ⚠️ Verify | Not guaranteed AA — use for decorative/secondary only |
| `--color-primary-on-brand` | `--color-primary-brand` | ✅ Passes AA | Branded buttons, highlights |
| `--color-intent-error-*` | surface | ⚠️ Verify | Check in both themes |
| `--color-intent-success-*` | surface | ⚠️ Verify | Green hues often fail 4.5:1 on light surfaces |
| `--color-intent-warning-*` | surface | ⚠️ Verify | Amber can fail on light |

### Getting the computed value for testing

MDS tokens are oklch — browsers compute them correctly, but colour pickers may not sample them directly.

``js
// Get computed hex-equivalent value
getComputedStyle(document.documentElement)
  .getPropertyValue('--color-on-surface')
  .trim()
``

The DevTools colour picker (click any colour swatch in the Styles panel) shows the computed RGB and its contrast ratio against the current background automatically when inspecting text elements.

For oklch-to-hex conversion: https://oklch.com

---

## Common contrast failure patterns in Merkle surfaces

### `--color-on-surface-subtle` as informational text
This token is intentionally lower contrast for decorative and secondary use. Never apply it to:
- Error messages or validation copy
- Required-field labels
- Link text where colour is the only differentiator
- Any text that carries the primary meaning

### Status intent colours without a text fallback
`--color-intent-success` (green) and `--color-intent-warning` (amber) can fail 3:1 against light surfaces. Always accompany intent-colour icons and badges with a text label or pattern, and verify the icon itself meets 3:1 against its background (WCAG 1.4.11 non-text contrast).

### Dark mode surprises
Token pairs that pass AA in light mode can produce lower contrast in dark mode because computed colours shift. The `--color-intent-*` tones are the most common offenders. Do not assume light-mode passes transfer to dark.

### Charts and data visualisation
Chart series colours (`--chart-1` through `--chart-N`) are not guaranteed to meet 3:1 against each other or against the chart background. When two series must be distinguishable:
1. Use both colour and shape/pattern (line style, fill pattern, point shape)
2. Verify adjacent series meet ≥ 3:1 against each other (WCAG 1.4.11)
3. Label series directly where possible rather than relying on a distant legend

---

## Quick testing workflow

1. Open the Merkle surface in Chrome
2. Open DevTools → Elements → Styles
3. Click any colour swatch — the picker shows contrast ratio inline for text elements
4. Set `data-theme="light"` on `<html>`, note ratios
5. Set `data-theme="dark"`, note ratios
6. For APCA spot-checks: https://www.myndex.com/APCA/
7. For systematic audits: run **axe DevTools** (browser extension) — flags WCAG 1.4.3 (contrast) automatically
