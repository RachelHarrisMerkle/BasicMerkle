
# Merkle PowerPoint Designer

**Scope: PowerPoint (.pptx) files only.** This skill edits and creates Merkle-branded `.pptx`
files. It does not apply to web, Figma, Google Slides, Keynote, Word, PDF, or any other format.

> **Legacy brand:** this skill uses **Proxima Nova / Arial**, the **`#040E4B` / `#0391F2`
> palette**, and the **`Merkle_2025_v2` theme**. It does not use MDS tokens, Work Sans, or the
> beta palette used by other Merkle Create skills.

This skill is fully self-contained — it does not require any other skill.

## Reference Files

Load only what you need for the current job:

| File | Load when |
|------|-----------|
| `brand-guidelines.md` | You need colors, fonts, layouts, or visual identity rules |
| `approach-a-patch.md` | Patching an existing deck (fonts + colors + theme) |
| `approach-b-rebuild.md` | Rebuilding slides from scratch using the master template |
| `slide-patterns.md` | You need exact XML for agenda slides, custom slides, or helper functions |


## Step 0 — Identify the Job and Check for the Master Template

### What is the user trying to do?

| Scenario | Input files expected |
|---|---|
| **Patch** an existing deck | Input deck + master template |
| **Rebuild** an existing deck | Input deck + master template |
| **Create from scratch** | Master template only — no input deck |

``bash
ls /mnt/user-data/uploads/*.pptx
``

### Template present?

- **Two or more `.pptx` files** → identify which is the input deck and which is the master template (the template is usually named `Merkle_PPT_Template.pptx` or similar). Proceed to Step 1.
- **One `.pptx` file + user is patching or rebuilding** → that file is the input deck; template is missing. See **No Template** below.
- **One `.pptx` file + user is creating from scratch** → that file may be the template. Confirm with the user, then proceed to Step 2 (skip Step 1 audit).
- **No `.pptx` files + user is creating from scratch** → template is missing. See **No Template** below.

### No Template — Fallback

If the master template is missing and the user cannot provide it:

1. **Share the download link:**

   > "You'll need the Merkle master template to proceed. You can download it here:
   > 📎 **[Download Merkle PPT Template](`TEMPLATE_DOWNLOAD_URL`)**
   > Once downloaded, upload it here alongside your deck and I'll get started."

   > ⚠️ `TEMPLATE_DOWNLOAD_URL` is a placeholder — replace with the hosted URL before deploying this skill.

2. **If the user is on Claude Desktop**, add this prompt:

   > "It looks like you're using the Claude desktop app. For the best experience uploading and downloading PowerPoint files, I recommend switching to the browser version at **claude.ai**, which has full file upload support."

3. **Patch-only fallback (existing deck, no template):** if the user explicitly wants to proceed without the template, apply fonts and colors only via Approach A and note the limitation in the Designer Review Summary:
   ``
   ⚠️  Master template not provided. Theme, backgrounds, and logo assets could not be applied.
       Fonts and colors patched only. Upload the Merkle master template for a full re-brand.
   ``
   This fallback does not apply to rebuild or from-scratch jobs — both require the template.


## Step 0.5 — Font Selection

Before any file work, ask the user to choose a font. See **Font Selection** in `brand-guidelines.md` for the exact prompt, decision guidance, default behaviour, and availability check.

Do not proceed until a font is confirmed or the default (Arial) has been applied.


## Step 1 — Audit the Deck

**Skip this step entirely if creating from scratch** — go directly to Step 2 (Approach B).

Unpack and read the deck before deciding on an approach:

``bash
python scripts/office/unpack.py input.pptx unpacked/
extract-text input.pptx
``

Run the layout audit (see `approach-a-patch.md` Step 1 for the full script). Key question: **are most slides on a generic DEFAULT layout?**

- **Yes (>30% DEFAULT/BLANK)** → deck was not built from the Merkle template → **use Approach B**
- **No** → deck uses Merkle layouts → **try Approach A first**


## Step 2 — Choose an Approach

| | Approach A — Patch | Approach B — Rebuild |
|---|---|---|
| **What it does** | Applies brand colors, fonts, and theme to existing slides | Replaces each slide with a fresh layout from the master template |
| **Fidelity** | Partial — visual structure stays as-is | Full — indistinguishable from the master template |
| **Speed** | Faster | Slower |
| **Requires template** | Yes (for theme XML, backgrounds, logos) | Yes |
| **Use when** | Deck is already close to on-brand | Deck was built from a different template, or >30% of slides look structurally wrong |

Read the relevant approach file before starting any file work.


## Step 3 — Non-Negotiable Requirements

Every output file must satisfy all three:

1. **Only the user-selected font is permitted** (Arial or Proxima Nova — confirmed in Step 0.5). No Calibri, Calibri Light, or any other typeface anywhere.
2. **The `Merkle_2025_v2` theme must be installed in the file.** Never deliver without it.
3. **Custom slides flagged for designer review.** Any slide that doesn't fit a standard Merkle layout gets a speaker note: `⚠️ DESIGNER REVIEW: Custom layout — verify fit and spacing.`

Full brand rules are in `brand-guidelines.md`.


## Step 4 — QA

After producing the output file, always run QA before delivering.

### Content check
``bash
extract-text output.pptx
extract-text output.pptx | grep -iE "\bx{3,}\b|lorem|ipsum|\bTODO|\[insert"
``

### Visual check
``bash
python scripts/office/soffice.py --headless --convert-to pdf output.pptx
rm -f slide-*.jpg
pdftoppm -jpeg -r 150 output.pdf slide
ls -1 "$PWD"/slide-*.jpg
``

Inspect each slide image for: overlapping elements, text overflow, off-brand colors, missing logos, structural issues. Fix and re-render until clean.


## Step 5 — Designer Review Summary

Every delivery must end with this summary. See `brand-guidelines.md` for the required format.


