# Approach B — Rebuild Workflow

Use when the deck was built from a completely different template, or when >30% of slides look structurally wrong after Approach A. Produces slides indistinguishable from the master template.

**Requires the master template file.**

---

## Step 1 — Map Content to Template Layouts

Review the input deck content and generate thumbnails for reference:

``bash
python scripts/thumbnail.py input.pptx input_thumbs/
python scripts/thumbnail.py template.pptx template_thumbs/
``

For each slide, decide which template layout to use (see `brand-guidelines.md` → Slide Layouts table).

Document the mapping before proceeding, e.g.:
``
Slide 1  → layout 4  (Title Page - Texture 3)
Slide 2  → layout 8  (Agenda - Texture)        ← use build_agenda_slide() helper
Slide 3  → layout 14 (Divider - Texture, Dark)
Slide 4  → layout 25 (Title & Body + EYEBROW)
``

**Flag any slide whose content cannot be mapped to a standard layout** — these are custom slides that need designer review (see `brand-guidelines.md`).

---

## Step 2 — Unpack Template; Build New Deck Shell

``bash
python scripts/office/unpack.py template.pptx template-unpacked/
python scripts/office/unpack.py template.pptx output-unpacked/   # start from a template copy
``

Remove all template placeholder slides from `output-unpacked/ppt/slides/` and clear `<p:sldIdLst>` in `presentation.xml`. The template's master, layouts, theme, media, and fonts all stay in place.

---

## Step 3 — Create Slides from Layouts

For each mapped slide, use `add_slide.py`:

``bash
python scripts/add_slide.py output-unpacked/ slideLayout14.xml
# Prints: <p:sldId id="XXXX" r:id="rIdN"/> — add this to <p:sldIdLst> in presentation.xml
``

---

## Step 4 — Populate Content into Placeholders

| `ph type` | Content |
|---|---|
| `title` | Slide title |
| `body` | Main body text / bullets |
| (none / `idx="1"`) | Subtitle or secondary body |
| `dt` | Date |
| `sldNum` | Slide number (leave as-is) |

**Always use string/regex for XML edits — never `ET.write()`** (namespace mangling corrupts files).

**Font:** use `Proxima Nova` if embedded in the template or installed on the system; otherwise `Arial`. See Font Selection in `brand-guidelines.md`.

**⚠️ Agenda slides — use `build_agenda_slide()` helper from `slide-patterns.md`, not placeholder population.** The Agenda - Texture layout (layout 8) has divider lines, number columns, and row spacing as free-floating shapes with exact EMU coordinates. Populating the placeholder directly produces incorrect vertical spacing and misaligned divider lines.

For custom slides that don't fit standard layouts, use the readable content distribution pattern from `slide-patterns.md`.

---

## Step 5 — Flag Custom Slides and Pack

Add speaker notes to all custom/non-standard slides (see `brand-guidelines.md` → Custom Slide Flagging), then:

``bash
python scripts/clean.py output-unpacked/
python scripts/office/pack.py output-unpacked/ output.pptx --original template.pptx
``

---

## Common Issues

| Issue | Cause | Fix |
|-------|-------|-----|
| Custom slide text overflows or is invisible | Content placed in wrong placeholder — `idx=12` is only 0.20" tall | Put all body content in `idx=11` (4.98" working area); use `idx=12` for eyebrow label only |
| File opens with repair dialog | `ET.write()` namespace mangling | Always use string/regex for XML edits |
| Agenda rows misaligned | Placeholder populated directly instead of using helper | Use `build_agenda_slide()` from `slide-patterns.md` |
| Leftover placeholder `X`/`x` bullets | Unfilled template content | Remove `<a:p>` blocks whose `<a:t>` text is only `X` or `x` |
| File opens as template / extension error | Source was `.potx` | Replace `presentationml.template.main+xml` with `presentationml.presentation.main+xml` in `[Content_Types].xml` |
