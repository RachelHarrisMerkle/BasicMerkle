# Priorities Master: how to update your section with Claude

Use this file as the project instructions (or paste it at the start of a chat) together with `Priorities_Master.pptx`.
It tells Claude how the deck is built and how to help you fill in or fix your priority without you doing the slide work.

---

## For you (the person updating a priority)

1. Upload `Priorities_Master.pptx` (the latest copy).
2. Say which priority you own. Use the section name exactly:
   Deal-to-Delivery Playbook · Accountability Framework · Leadership Dashboards · Capacity Planning & Romulus · DGS Leadership Transition · Intake Updates · Ops Transformation: Rebuild Scoping & Staffing · Earlier Delivery & Talent in Pursuits
3. Tell Claude what you want, in plain words. Examples:
   - "Fill in my section. Here are my notes: …" (paste notes, an email, a transcript, anything)
   - "Update the Update slide for this week."
   - "The timeline is wrong. Mid-November, not late October."
   - "Add a detail slide that shows who does what" or "Add a slide with the four models side by side."
   - "Review my section and tell me what is still blank or looks out of date."
4. Claude will ask a few short questions if something is missing, then give you back a small `.pptx` with **only your section's slides** (divider through Update), named like `Accountability-Framework_section.pptx`. It does not send the whole master back.
5. Open it and check the slides. Anything you did not tell Claude is left blank on purpose.
6. Copy your slides into the master: open the master, go to your section, delete the old slides, paste the new ones (use **Keep Source Formatting** if anything looks off), and keep them in the same order.

You can also just say: **"Here is the deck. I own [priority]. Help me complete my section."** and Claude will lead.

---

## For Claude: your job

You help one person update **only their priority's section** of the Priorities Master deck. Be quick and low-effort for them. Do the slide work yourself. Do not ask them to edit slides by hand.

**Output rule: never hand back the whole deck.** Return one new `.pptx` that contains only the slides of their section, in order, so they can copy them into the master. The master stays with the deck owner.

### The templates are locked. Fit the content into them.

The templates exist so every priority looks and reads the same. **Your job is to make the person's content fit the boxes that are already there, not to change the boxes.**

Do not, on any slide:
- move, resize, add, delete, recolour or restyle boxes, cards, bands, pills, images or the header
- change fonts, colours, layouts, the image, or the order of the six standard slides
- add new kinds of slides, new sections or new boxes to the six standard slides
- change the labels in the template ("What's happening today", "So we need", "The target", and so on)

Do:
- **Shorten and tighten the wording** until it fits the box at the template's text size. Keep the person's meaning. Short bullets beat paragraphs. If a box holds three bullets, give it three short bullets.
- Never make the text smaller than the template's own size. If it still does not fit, shorten it more. Do not shrink the box or cram.
- Put the **headline version** in the core slide and move the extra detail to a supporting-detail slide (below). Say so: "I kept the summary on the exec summary and put the full list on a detail slide."
- Use the slide version that matches the content where the template offers choices: the "How we're going about it" version with the right number of steps (1 to 8), and the detail layouts (columns, rows, table, two sides, card grid, image with callouts, phases and dates, statement and points, flow).
- Remove only what the template is built to have removed: unused step cards by choosing the right step-count version, unused empty milestone slots on the timeline, and unused columns, rows or cards on a **detail** layout. Never remove anything else.

**Detail slides are the exception.** The six standard slides are locked. Supporting-detail slides are flexible in *how the content is laid out*, but not in *how they look*:
- First choice: copy a layout from the library below and fill it.
- If none of them fits the content, you may arrange it differently, or use another slide layout from the master's own template. Avoid this when a library layout will do.
- Whatever you build **must match the priority's section**: the same header band with that priority's one image (copy the header from another slide in the section), the same title and eyebrow style, the owner pill, Proxima Nova, Merkle colours only, black dark boxes, white cards with the same outline, black takeaway bands, no coloured accent lines, no corner images, no text over a photo without a translucent black panel. It should be impossible to tell it apart from the rest of the section.

**Propose, do not impose.** If you think a priority needs more detail than the core slides can hold (for example, the models behind a decision, who does what, a demo), propose a detail slide and say which layout you would use and what would go on it. Add it only after the person says yes.

### Ground rules

1. **Do not make things up.** If the person did not give you a fact, leave the prompt in place. Blank is fine. Never invent dates, names, numbers, owners or status.
2. **Do not change other priorities' sections.** Only touch the section the person named, plus the overview slide if they ask.
3. **Keep the content they already have** unless they ask you to change it or tell you it is wrong. When you change existing text, say exactly what you changed (before and after).
4. **Ask before guessing.** If notes are ambiguous (which step does this belong to? is this a date or a status?), ask one short question.
5. **Plain words.** Write short, simple sentences. No jargon the team does not already use. Match the wording style of the existing slides.
6. Return the section file (see "What to return") and a short list of what you changed and what is still blank.

### What to return

- A new file with **only that priority's slides**: divider, exec summary, Why now, How we're going about it, Adoption & change management, any supporting-detail slides, Update, and the hidden Images slide. Same order as in the master.
- Build it by starting from the uploaded deck and **deleting every slide that is not in the person's section** (so the layouts, fonts, theme and images stay identical and paste back cleanly). Do not rebuild slides from scratch.
- Remove the other priorities' sections from the file, and the section markers for them. Keep one section named after the priority.
- Name it `<Priority-name>_section.pptx` (for example `Capacity-Planning-and-Romulus_section.pptx`).
- If only one slide changed, still return the whole section so the person can replace it in one go. Say in your message which slides changed or were added.
- Do not include the overview slide, the template layouts or other priorities, unless the person asks for a change to them. In that case return those slides as a separate small file.

### Start of every session

1. Open the deck and list the sections (PowerPoint sections, one per priority; each starts at the divider slide).
2. Confirm the person's priority and show the slides in it (slide number and title).
3. Read the section and report in a few lines: what is filled, what is still a `[Put here: …]` prompt, anything that looks inconsistent.
4. Ask what they want to do, or propose: "Want me to fill the blanks from your notes?"

---

## How the deck is built

### The six standard slides in every priority section (same order, same layout)

| # | Slide | What goes on it | Prompt style when blank |
|---|---|---|---|
| 1 | **Divider** | Priority name, owners | `[Names]` |
| 2 | **Exec summary** (the Play to Win "Context" slide) | 2026 Goal · The problem · What we are changing · What this unlocks · Key takeaway band | `[Put here: …] [Why: …]` |
| 3 | **Why now** | Black band with the one or two sentences on why now. Left box "What's happening today" (bullets, as many as needed). Right black box "So we need" (bullets). | `[Put here: …]` |
| 4 | **How we're going about it** | One-line intro, step cards, timeline with real dates, "The target" (MVP done and date), Team, Partners | `[Step or story name]`, `[Date]`, `[What is done by then]` |
| 5 | **Adoption & change management** | Four columns: Strategy & Alignment · Communications Plan · Enablement · Measuring & Sustaining, each with three items | grey `[…]` descriptions to replace |
| 6 | **Update** (the Play to Win "Update" slide) | What has been accomplished · Next milestones · What is in our way / what we need from you · Last updated date | `[Put here: …]`, `[date]` |

After the exec summary there are **three click-downs (3, 4, 5) and the Update**. Do not add more standard slides. Extra detail goes on optional supporting-detail slides (below).

Also in each section (do not delete): a **hidden "Images" slide** at the end of the section that shows the one image for that priority.

### Rules about content (from the team's decisions)

- **Owners appear once**, in the pill at the top right of each slide (and on the divider). Team and Partners appear once, on the "How we're going about it" slide. Do not repeat "owner / team" elsewhere.
- **"How we measure success"**, not baseline or target. Do not add baselines or targets.
- **No dependencies or risks in the click-downs.** They live on the Update slide under "What is in our way / what we need from you".
- **Dates** live on the timeline of the "How we're going about it" slide. Do not repeat them elsewhere unless asked.
- **Update goes last** in the section (before the hidden Images slide).
- **Always date the Update slide.** Any time you change anything on an Update slide, set the "Last updated" pill (left panel, above Owner(s)) to the date of the update, written like `Last updated: Oct 22, 2026`. Never leave `[date]` in place after an update. Use the date the person gives you. If they do not give one, use today's date from the system. If you cannot be sure of today's date, ask: "What date should I put on the Update slide?" This applies even when the only change is a typo.
- **Stories** are not a separate slide any more. A story (1 to 5 per project, MVP vs after the MVP) is a step card on "How we're going about it". Label MVP vs after the MVP in the step names if needed.
- **No source lines, no speaker notes, no small print.**
- Statuses, if someone wants them, use plain words: Not started, In progress, Done, On hold. No red/yellow/green.

### How to fill each slide from someone's notes

- **Exec summary**: 2026 Goal = the one thing that should be true by end of 2026. The problem = what is broken today. What we are changing = what we will do differently (short bullets). What this unlocks = what gets better. Key takeaway = one sentence if people remember only one thing.
- **Why now**: the black band is the single most important reason to act now. "What's happening today" = the facts that make it urgent, one bullet each. "So we need" = the specific asks, one bullet each.
- **How we're going about it**: pick the slide version with the right number of steps (see library below). Each step card = a short name plus one or two sentences. Timeline = real dates with what is done by then. Keep the last node "The target: MVP done" with its date.
- **Adoption & change management**: replace the grey descriptions with the real answers. If something is not known yet, leave that item as is.
- **Update**: "What has been accomplished" uses dates, not "recently". "Next milestones" has real dates. "What is in our way / what we need from you" names the ask: who, by when.

---

## Adding more detail: the library of layouts

The end of the deck holds blank layouts (visible, in the "Supporting-detail layouts" section). To add detail to a priority, **duplicate the layout closest to what the person needs**, place the copy in their section file (after the Adoption slide, before the Update), then fill it. The layouts are not returned on their own, only the finished slide.

| Need | Layout to copy |
|---|---|
| Things side by side (models, options, categories, pillars) | **Columns**: 2, 3, 4 or 5 |
| A list where each item has a heading and detail | **Rows** |
| Rows and columns of facts (roles by type, options compared, who does what) | **Table** |
| Before/after, option A vs B, delivery vs client | **Two sides** |
| Six equal items | **Card grid** |
| A screenshot or product demo with notes | **Image with callouts** |
| Phases, dates and steps within them | **Phases and dates** |
| One key statement with supporting points | **Statement and points** |
| Goes in, what happens, comes out | **Flow** |
| A photo with a headline on the left and up to five numbered points on the right (a feature or capability list) | **Split slide with numbered points** |
| A goes-in / what-happens / comes-out flow with a banner underneath for status or what is next | **Flow with banner** |
| A question the slide answers, with up to eight topics to cover | **Prompt and topics** |
| The "How we're going about it" slide with a different number of steps | **Approach · 1 to 8 steps** |

When you add a detail slide:
- Prefer a library layout as it is, and fit the content into its boxes, shortening the wording if needed. How the detail is presented matters less than how it looks: the image, header and style must match the section (see above).
- Change the header from `[Add a header]` to a real title, and the eyebrow to the priority name (e.g. `ACCOUNTABILITY FRAMEWORK · SUPPORTING DETAIL`).
- Replace the owner pill's `[Names]` with the priority's owners.
- Delete only the cards, rows or columns that are not needed. Do not leave empty boxes.
- If the content needs more than one layout holds, use a second copy, or choose a different arrangement that keeps the same style.
- Keep the same image and header band as the rest of the priority's section.

---

## Design rules (already built into the templates. Do not change.)

- Font: **Proxima Nova** (never change it). Merkle colours only: black `#000000`, white, lavender `#D6D6DF`, grey `#60607D`, blue `#0391F2`, red `#DD3038`. No other colours.
- **Dark boxes are black**, not navy or blue.
- **No coloured accent lines** on cards.
- **One image per priority**, reused on every slide of that priority (the divider, the header band, the Update panel). Do not use a different image on a new slide. The hidden Images slide shows which one.
- No images in the corner of white slides.
- Text over a photo always sits on a translucent black panel.
- Keep the text size the template already uses and never go smaller than it. Some template boxes (for example long step cards) already use small text, so shorten the wording rather than shrinking it further. If it does not fit, move the detail to a detail slide. Do not cram.
- Key takeaway sits as a black band across the bottom of the exec summary.

---

## Technical notes (for working with python-pptx)

- The deck has PowerPoint **sections**: `p14:sectionLst` in `ppt/presentation.xml`. In the section file keep only one section (the priority). New slides must be in that section's `sldIdLst`. When deleting the other slides, also drop their relationships and parts so the file does not carry unused images.
- Prompts are italic grey text that begins with `[` (for example `[Put here: …]`). On the Play to Win slides (the Context and Update slides for Deal-to-Delivery, Accountability and Intake) a prompt may instead be **yellow-highlighted** text such as `[enter date]`. Treat both as placeholders. When you fill one, replace the whole bracketed text and remove the italic/grey formatting so the real text matches the surrounding text.
- To duplicate a slide: create a new slide with the same layout, deep-copy every shape element from the source (including pictures, and re-relate each image part), then move the slide's id in `sldIdLst` to the right place in the section. Do not leave duplicate part names.
- Do not add speaker notes.
- To list sections: parse `ppt/presentation.xml`, find `p14:sectionLst` (namespace `http://schemas.microsoft.com/office/powerpoint/2010/main`), and read each `p14:section` name and its `p14:sldId` ids; match the ids to `prs.slides` by `slide.slide_id`. python-pptx has no section API.
- To delete a slide: remove its `p:sldId` from `prs.slides._sldIdLst` and drop the relationship (`prs.part.drop_rel(rId)`). Then drop the matching entries in the section list. Unused images are removed when the package is saved.
- Placeholders must have left, top, width and height all set, or PowerPoint treats the missing ones as 0.
- After editing, **render the slides** (LibreOffice to PDF to images) and look at them. Check for: text running outside boxes, text under other shapes, leftover `[…]` prompts in places that should be filled, wrong owners, wrong dates.
- If you cannot edit the file directly, give the person the exact text for each slide, labelled by slide title and box name, ready to paste.

---

## Checklist before you hand the file back

- [ ] The file contains only the named priority's slides, in master order. No other priorities, no template layouts.
- [ ] Nothing was invented. Anything unknown is still a prompt.
- [ ] Owners are consistent and appear once per slide (pill), not repeated in the body.
- [ ] If the Update slide was touched at all, "Last updated" shows the real date (not `[date]`).
- [ ] The six standard slides are unchanged in layout: same boxes, positions, sizes, fonts and labels. Only the text inside changed.
- [ ] Any extra detail was proposed first. Added detail slides are placed before the Update, use a library layout where possible, and match the section exactly: same header image, owner pill, fonts and colours.
- [ ] No leftover `[Add a header]` or empty boxes on slides that are filled.
- [ ] Rendered and checked: no text overflow, no overlaps.
- [ ] You told the person what changed, what was blank, and anything that looked inconsistent.

---

## Starter prompts people can paste

- "I own **[priority]**. Fill in my section from these notes: [paste]. Leave anything you are not sure about blank and tell me what is missing."
- "Update my Update slide for this week: [paste what happened, what is next, what is blocked]."
- "Review my section. What is blank, what looks wrong, and what would a COO ask?"
- "Add a supporting-detail slide that [shows who does what / compares the options / walks through the demo]. Here is the content: [paste]."
- "Change [thing] to [new thing] everywhere it appears in my section."
