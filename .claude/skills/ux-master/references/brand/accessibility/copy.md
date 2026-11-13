# Copy accessibility — Merkle Accessibility Advocate

Copy accessibility ensures meaning is conveyed through language, not assumed from visual context. These rules apply to every text element written for a Merkle surface.

---

## Alt text

Alt text conveys the *meaning* of an image to someone who cannot see it — not a description of visual properties.

### Classify the image first

| Image type | What to write | Example |
|---|---|---|
| **Informative** — content the image carries | Describe the key information | `alt="Bar chart showing digital revenue up 79% year-on-year"` |
| **Functional** — linked or interactive image | Describe its purpose/destination | `alt="Merkle homepage"` (on a logo that links to `/`) |
| **Decorative** — adds no information | Empty string | `alt=""` |
| **Complex** — chart, diagram, infographic | Short alt (the headline takeaway) + longer description nearby | `alt="Customer journey stages"` + a visible prose block or data table below |

### What not to write
- "Image of…" / "Photo of…" — screen readers already announce the element type
- The filename (`photo_2943.jpg`, `hero-background.png`)
- A description that duplicates the adjacent heading or caption — users hear it twice
- "Decorative" when `alt=""` is the correct signal

### Merkle-specific: brand icons in functional context
The Create Hub brand icon picker renders icons as decorative (`alt=""` / `aria-hidden="true"`). When an icon appears in a functional role — an icon-only button, a status indicator — it needs either an `aria-label` on the parent button or a visually-hidden label. The icon SVG itself takes `aria-hidden="true"` in both cases.

---

## Form labels

Every form input must have an accessible name — the label a screen reader announces when the user reaches the field.

### Providing an accessible name (in order of preference)

1. **Visible `<label>` element** — always prefer this. Taps/clicks on the label focus the input; sighted and screen reader users both benefit.
2. **`aria-label`** — for inputs where a visible label is inappropriate (e.g., a standalone search bar with an icon but no text).
3. **`aria-labelledby`** — when the accessible name comes from an existing text element elsewhere in the DOM.

``tsx
// Preferred — visible label
<label htmlFor="email">Email address</label>
<input id="email" type="email" />

// Acceptable — aria-label for icon-search
<input aria-label="Search" type="search" />

// Never — placeholder is not a label
<input placeholder="Email address" type="email" />
``

Placeholder text disappears when the user starts typing. It cannot replace a label for users who pause mid-form or use autofill.

### Required fields
Mark required fields with both `aria-required="true"` **and** a visible indicator. The visible indicator should be text ("required" in a hint, or an asterisk with a legend) — not colour alone. For MDS form components, pass `aria-required` as a prop; it flows through to the underlying element.

### Field hints and descriptions
Associate hint text to the input via `aria-describedby`:

``tsx
<label htmlFor="password">Password</label>
<input id="password" aria-describedby="password-hint" type="password" />
<p id="password-hint">Must be at least 8 characters and include a number.</p>
``

---

## Error messages

Error messages must be understandable, associated with the relevant field, and announced automatically to screen reader users.

### Writing the message
1. Say what went wrong in plain language — no technical strings, no codes
2. Say what to do next — "Enter a valid email address" not "Invalid input"
3. Do not blame the user — "That email address isn't valid" not "You entered an incorrect email"

### Programmatic association

``tsx
<label htmlFor="email">Email address</label>
<input
  id="email"
  type="email"
  aria-describedby={hasError ? "email-error" : undefined}
  aria-invalid={hasError || undefined}
/>
{hasError && (
  <p id="email-error" role="alert">
    Enter a valid email address (e.g., name@merkle.com).
  </p>
)}
``

- `aria-invalid="true"` signals the field is in an error state
- `role="alert"` causes the message to be announced immediately when it appears — without requiring the user to move focus to it
- Do not apply `role="alert"` to static content; only to errors that appear dynamically

### Form-level errors (multiple fields)
When a submission fails with multiple errors, announce a summary:

``tsx
<div role="alert" aria-live="assertive">
  <p>3 fields need attention. Review the highlighted fields below.</p>
</div>
``

Move focus to this summary or to the first error field after the failed submission attempt.

---

## Link text

Link text must describe the destination or action on its own — not rely on surrounding context.

| Avoid | Write instead | Why |
|---|---|---|
| "Click here" | "Read the 2026 CX Imperatives report" | Destination unknown without context |
| "Read more" | "Read the case study: Burger King loyalty programme" | Screen reader users navigate a list of links — "read more" appears 12 times |
| "here" | Describe the linked page | Same problem as "click here" |
| "Download" (bare) | "Download the Q1 2026 earnings report (PDF, 1.2 MB)" | Describes what's being downloaded |

### Duplicate links on the same page
If the same destination appears multiple times (card grid with "Learn more" links), each must have a unique accessible name via `aria-label` or `aria-labelledby`:

``tsx
<a
  href="/case-study/toyota-loyalty"
  aria-label="Read case study: Toyota loyalty programme"
>
  Learn more
</a>
``

---

## Icon-only button labels

Buttons that contain only an icon must have an accessible name. The icon SVG must be hidden from assistive technology.

``tsx
// MDS ButtonPrimitive — icon-only
<ButtonPrimitive data-ui="button" aria-label="Close dialog">
  <XIcon aria-hidden="true" />
</ButtonPrimitive>
``

### Writing icon-only labels
- Use verb + object: "Close dialog", "Delete file", "Share report"
- Match the verb to the action, not the icon: "Filter results" not "Funnel"
- Keep under 8 words

The MDS dev-time guard throws in development when `iconOnly` is set without an `aria-label` — that's the safety net. The copy responsibility is choosing a label that accurately describes the action.

---

## Headings and document structure

Headings communicate page structure to screen reader users who navigate by them. A heading is a structural landmark, not just large styled text.

- Use heading levels semantically: `h1` is the page title, `h2` for major sections, `h3` for sub-sections — no level skipping
- Never use a heading tag for visual styling — use a styled `<p>` or `<span>` instead
- One `h1` per page

For Fumadocs MDX pages on the Create Hub: the page title from frontmatter generates the `h1`. Begin content-level headings at `##` (which maps to `h2`).
