# Component accessibility — Merkle Accessibility Advocate

MDS components are built on Base UI v1.5. Base UI owns the ARIA contract for complex interactive widgets — roles, states, keyboard behaviour, and focus management. Your responsibility is to provide accessible names, descriptions, and the correct markup context around Base UI primitives.

**The key rule:** If you find yourself adding `role`, `aria-expanded`, `aria-selected`, `aria-controls`, or `aria-haspopup` to a Base UI component, stop — Base UI already manages these. Adding them creates conflicts and incorrect states.

---

## Base UI component ARIA guide

### Button (`data-ui="button"`)

Base UI ButtonPrimitive renders a native `<button>` element. Native buttons have `role="button"` implicitly and respond to Enter and Space natively.

**Your responsibilities:**

``tsx
// Icon-only — aria-label on the button, aria-hidden on the icon
<ButtonPrimitive data-ui="button" aria-label="Delete file">
  <TrashIcon aria-hidden="true" />
</ButtonPrimitive>

// Toggle — aria-pressed changes between true/false
<ButtonPrimitive
  data-ui="button"
  aria-pressed={isBold}
  onClick={() => setIsBold(b => !b)}
>
  Bold
</ButtonPrimitive>

// Loading — aria-busy signals in-progress, label describes the waiting state
<ButtonPrimitive
  data-ui="button"
  aria-busy={isLoading}
  aria-label={isLoading ? "Saving, please wait" : undefined}
>
  {isLoading ? <SpinnerIcon aria-hidden="true" /> : "Save"}
</ButtonPrimitive>
``

The MDS dev guard throws in development when `iconOnly && !aria-label` — that's the safety net, not the specification.

### Dialog (`data-ui="dialog"`)

Base UI Dialog manages: focus trap on open, return focus to trigger on close, `aria-modal="true"`, `role="dialog"`.

**Your responsibilities:**

``tsx
<Dialog.Root>
  <Dialog.Trigger render={<button>Open settings</button>} />
  <Dialog.Popup>
    {/* Title is required — Base UI links it to the dialog automatically */}
    <Dialog.Title>Account settings</Dialog.Title>
    {/* Description is optional but recommended for complex/destructive dialogs */}
    <Dialog.Description>
      Changes save immediately. Contact support to recover deleted data.
    </Dialog.Description>
    {/* ... content ... */}
    <Dialog.Close render={<button>Close</button>} />
  </Dialog.Popup>
</Dialog.Root>
``

Do not add `aria-labelledby` or `aria-describedby` manually — Base UI links `Dialog.Title` and `Dialog.Description` automatically.

For dialogs without a visible title (rare — avoid if possible), use `aria-label` on `Dialog.Popup`:
``tsx
<Dialog.Popup aria-label="Confirm deletion">
``

### Tabs (`data-ui="tabs"`)

Base UI Tabs manages: `role="tablist"`, `role="tab"`, `role="tabpanel"`, `aria-selected`, `aria-controls`, and arrow-key navigation between tabs.

**Your responsibilities:**
- Tab labels must be unique and descriptive — not "Tab 1", "Tab 2"
- Panel content that loads asynchronously: use `aria-busy="true"` on the panel while loading

Keyboard behaviour managed by Base UI: `←`/`→` arrows move between tabs; `Tab` moves focus into the active panel.

### Accordion (`data-ui="accordion"`)

Base UI manages: `aria-expanded`, `aria-controls`, trigger activation via Enter/Space.

**Your responsibilities:**
- Trigger text must describe what's in the panel — not a generic "Expand"
- Do not nest interactive elements (another button, a link) inside the trigger element

### Select

Base UI manages: `role="listbox"`, `role="option"`, `aria-selected`, keyboard navigation (arrows, Enter, Escape, character search).

**Your responsibilities:**
- The trigger must have a visible label (via adjacent `<label>` or `aria-label` on the trigger)
- Selected value displayed in the trigger must reflect the actual current value

---

## Keyboard navigation requirements

Every MDS interactive surface must be fully operable by keyboard alone.

| Key | Expected behaviour |
|---|---|
| `Tab` | Move focus to the next interactive element |
| `Shift+Tab` | Move focus to the previous interactive element |
| `Enter` / `Space` | Activate buttons, open/close select, check/uncheck checkboxes |
| `↑` `↓` | Move through options in listboxes, menus, and radio groups |
| `←` `→` | Move between tabs; navigate radio groups |
| `Escape` | Close dialogs, menus, and popovers; return focus to trigger |
| `Home` / `End` | First/last item in a listbox or menu |

### Building custom composite widgets
If a component is not based on a Base UI primitive, follow the ARIA Authoring Practices Guide (APG) patterns: https://www.w3.org/WAI/ARIA/apg/patterns/

### `tabIndex` rules
- `tabIndex="0"` — makes a non-interactive element tab-reachable (rare; use a real interactive element instead)
- `tabIndex="-1"` — enables programmatic `.focus()` without adding to tab order (valid for focus management)
- `tabIndex > 0` — **never use**; breaks the natural tab order for keyboard users

---

## Focus management

### Focus must always be visible

MDS provides `:focus-visible` styles on all interactive components. Do not suppress `outline` without an equivalent replacement.

``css
/* Never */
:focus { outline: none; }

/* If you must override, provide an equivalent indicator */
:focus-visible {
  outline: 2px solid var(--color-primary-brand);
  outline-offset: 2px;
}
``

### Dialog focus on open and close

When a Dialog opens, Base UI moves focus to the first focusable element inside the dialog (or to `Dialog.Popup` itself if nothing else is focusable). When it closes, focus returns automatically to the element that triggered it.

Do not add manual `.focus()` calls around Base UI Dialog unless you are triggering the dialog imperatively (not in response to a user click) — in that case, you are responsible for returning focus when it closes.

### Focus after dynamic content appears

When new content appears that the user must act on (a confirmation, an inline form, an error summary), move focus explicitly:

``tsx
// Move focus to the error summary after a failed form submission
const summaryRef = useRef<HTMLDivElement>(null);

const handleSubmit = async () => {
  const result = await submitForm();
  if (!result.ok) {
    summaryRef.current?.focus();
  }
};

<div ref={summaryRef} tabIndex={-1} role="alert">
  {errors.length} fields need attention.
</div>
``

---

## Live regions for dynamic content

Use `aria-live` for content that updates without a page navigation.

``tsx
// Urgent announcements — errors, warnings — interrupt current narration
<div role="alert">
  {error && <p>Payment failed. Check your card details and try again.</p>}
</div>

// Non-urgent status — save confirmation, progress — wait for current narration to finish
<div role="status" aria-live="polite">
  {saved && <p>Changes saved.</p>}
</div>
``

- `role="alert"` is equivalent to `aria-live="assertive"` + `aria-atomic="true"` — it interrupts the user immediately. Reserve it for genuinely urgent messages (errors, warnings)
- `role="status"` (`aria-live="polite"`) waits for the current narration to finish — appropriate for save confirmations and non-critical updates
- Do not use either on static content; only on regions that update dynamically

---

## Testing interactive accessibility

1. **Tab through the page** — every interactive element must be reachable and show a visible focus indicator
2. **Activate all controls by keyboard** — Enter/Space for buttons, arrows for lists/tabs
3. **Open and close dialogs/menus** — verify focus returns to the trigger element on close
4. **Trigger form errors** — verify error messages are announced (use VoiceOver on Mac: `Cmd+F5`; NVDA on Windows; or the Chrome Screen Reader extension)
5. **Run axe DevTools** — flags ARIA violations and missing accessible names automatically
