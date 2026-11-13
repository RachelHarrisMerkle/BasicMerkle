# Slide Patterns

Known-good XML patterns for slide types that cannot be reliably reconstructed from layout placeholders alone. Use these directly — generating from scratch produces visually incorrect results even if the file is technically valid.

---

## Font Variable

Set `BRAND_FONT` once at the top of your script, based on the font confirmed in Step 0.5
(see `brand-guidelines.md` → Font Selection). All helpers below use this variable.

``python
# Set based on the font selection from Step 0.5. Default to Arial for safety.
# Replace with "Proxima Nova" if the user selected it and availability was confirmed.
BRAND_FONT = "Arial"
``

---

## Agenda Slide (layout 8 — Agenda - Texture)

The agenda layout's visual structure — numbered rows, divider lines, and spacing — is built from individual free-floating shapes, not the layout placeholder. The coordinates below are pixel-perfect values validated against the Merkle master template.

### Shape Spec

- Slide dimensions: 12192000 × 6858000 EMU
- Content area (left half): `x=502920`, width spans to `x+5303520`
- Right half: geometric image comes from layout master — do not add a background shape

### Exact Coordinates

| Element | x | y | cx | cy | Notes |
|---------|---|---|----|----|-------|
| AGENDA label | 502920 | 502920 | 4572000 | 256032 | sz=900, b=1, spc=400, color=`888888` |
| Top rule | 502920 | 905256 | 5303520 | 10973 | fill+stroke `333333` |
| Row N number | 502920 | see table | 502920 | 347472 | sz=1200, b=1, color=`555555` |
| Row N text | 1078992 | see table | 5120640 | 347472 | sz=1800, color=`FFFFFF` |
| Row N divider | 502920 | see table | 5303520 | 10973 | fill+stroke `333333` (omit after last row) |

> **Color note:** `#333333` (divider lines) and `#555555` (row numbers) are intentional
> Merkle template design colors — do NOT remap them. They are excluded from the color
> remap table in `approach-a-patch.md` for this reason.

### Row Y Positions (up to 7 sections)

| Row | Row y | Divider y |
|-----|-------|-----------|
| 1 | 987552 | 1408176 |
| 2 | 1490472 | 1911096 |
| 3 | 1993392 | 2414016 |
| 4 | 2496312 | 2916936 |
| 5 | 2999232 | 3419856 |
| 6 | 3502152 | 3922776 |
| 7 | 4005072 | — (no divider after last row) |

**Critical:** all text shapes must have zero internal padding:
``xml
<a:bodyPr wrap="square" lIns="0" tIns="0" rIns="0" bIns="0" rtlCol="0" anchor="ctr"/>
``
Omitting `lIns/tIns/rIns/bIns="0"` causes text to sit too low and misalign with divider lines.

### Python Helper

``python
def esc(t):
    return t.replace('&','&amp;').replace('<','&lt;').replace('>','&gt;')

def agenda_num_sp(sp_id, y, number):
    # Row 1 uses schemeClr for slightly lighter gray; rows 2-7 use srgbClr 555555
    if number == "01":
        fill = '<a:solidFill><a:schemeClr val="tx1"><a:lumMod val="50000"/><a:lumOff val="50000"/></a:schemeClr></a:solidFill>'
    else:
        fill = '<a:solidFill><a:srgbClr val="555555"/></a:solidFill>'
    return f'''<p:sp>
      <p:nvSpPr><p:cNvPr id="{sp_id}" name="Num {number}"/><p:cNvSpPr/><p:nvPr/></p:nvSpPr>
      <p:spPr>
        <a:xfrm><a:off x="502920" y="{y}"/><a:ext cx="502920" cy="347472"/></a:xfrm>
        <a:prstGeom prst="rect"><a:avLst/></a:prstGeom><a:noFill/><a:ln/>
      </p:spPr>
      <p:txBody>
        <a:bodyPr wrap="square" lIns="0" tIns="0" rIns="0" bIns="0" rtlCol="0" anchor="ctr"/>
        <a:lstStyle/>
        <a:p><a:pPr marL="0" indent="0"><a:buNone/></a:pPr>
          <a:r><a:rPr lang="en-US" sz="1200" b="1" dirty="0">
            {fill}<a:latin typeface="{BRAND_FONT}" pitchFamily="34" charset="0"/>
          </a:rPr><a:t>{esc(number)}</a:t></a:r></a:p>
      </p:txBody></p:sp>'''

def agenda_text_sp(sp_id, y, text):
    return f'''<p:sp>
      <p:nvSpPr><p:cNvPr id="{sp_id}" name="Section {text[:20]}"/><p:cNvSpPr/><p:nvPr/></p:nvSpPr>
      <p:spPr>
        <a:xfrm><a:off x="1078992" y="{y}"/><a:ext cx="5120640" cy="347472"/></a:xfrm>
        <a:prstGeom prst="rect"><a:avLst/></a:prstGeom><a:noFill/><a:ln/>
      </p:spPr>
      <p:txBody>
        <a:bodyPr wrap="square" lIns="0" tIns="0" rIns="0" bIns="0" rtlCol="0" anchor="ctr"/>
        <a:lstStyle/>
        <a:p><a:pPr marL="0" indent="0"><a:buNone/></a:pPr>
          <a:r><a:rPr lang="en-US" sz="1800" dirty="0">
            <a:solidFill><a:srgbClr val="FFFFFF"/></a:solidFill>
            <a:latin typeface="{BRAND_FONT}" pitchFamily="34" charset="0"/>
          </a:rPr><a:t>{esc(text)}</a:t></a:r></a:p>
      </p:txBody></p:sp>'''

def agenda_line_sp(sp_id, y):
    return f'''<p:sp>
      <p:nvSpPr><p:cNvPr id="{sp_id}" name="Divider"/><p:cNvSpPr/><p:nvPr/></p:nvSpPr>
      <p:spPr>
        <a:xfrm><a:off x="502920" y="{y}"/><a:ext cx="5303520" cy="10973"/></a:xfrm>
        <a:prstGeom prst="rect"><a:avLst/></a:prstGeom>
        <a:solidFill><a:srgbClr val="333333"/></a:solidFill>
        <a:ln w="12700"><a:solidFill><a:srgbClr val="333333"/></a:solidFill>
          <a:prstDash val="solid"/></a:ln>
      </p:spPr>
      <p:txBody><a:bodyPr/><a:lstStyle/><a:p><a:endParaRPr lang="en-US"/></a:p></p:txBody>
    </p:sp>'''

def build_agenda_slide(sections):
    """
    sections: list of (number_str, section_name) tuples, e.g. [("01", "Overview"), ...]
    Returns complete slide XML string ready to write to ppt/slides/slideN.xml
    Supports up to 7 sections; pass a shorter list for fewer rows.
    """
    ROW_YS  = [987552, 1490472, 1993392, 2496312, 2999232, 3502152, 4005072]
    LINE_YS = [1408176, 1911096, 2414016, 2916936, 3419856, 3922776]

    shapes = []
    sp_id = 3

    # AGENDA eyebrow label
    shapes.append(f'''<p:sp>
      <p:nvSpPr><p:cNvPr id="{sp_id}" name="AGENDA Label"/><p:cNvSpPr/><p:nvPr/></p:nvSpPr>
      <p:spPr>
        <a:xfrm><a:off x="502920" y="502920"/><a:ext cx="4572000" cy="256032"/></a:xfrm>
        <a:prstGeom prst="rect"><a:avLst/></a:prstGeom><a:noFill/><a:ln/>
      </p:spPr>
      <p:txBody>
        <a:bodyPr wrap="square" lIns="0" tIns="0" rIns="0" bIns="0" rtlCol="0" anchor="ctr"/>
        <a:lstStyle/>
        <a:p><a:pPr marL="0" indent="0"><a:buNone/></a:pPr>
          <a:r><a:rPr lang="en-US" sz="900" b="1" kern="0" spc="400" dirty="0">
            <a:solidFill><a:srgbClr val="888888"/></a:solidFill>
            <a:latin typeface="{BRAND_FONT}" pitchFamily="34" charset="0"/>
          </a:rPr><a:t>AGENDA</a:t></a:r></a:p>
      </p:txBody></p:sp>''')
    sp_id += 1

    # Top rule
    shapes.append(agenda_line_sp(sp_id, 905256)); sp_id += 1

    for i, (num, name) in enumerate(sections):
        shapes.append(agenda_num_sp(sp_id, ROW_YS[i], num)); sp_id += 1
        shapes.append(agenda_text_sp(sp_id, ROW_YS[i], name)); sp_id += 1
        if i < len(LINE_YS):
            shapes.append(agenda_line_sp(sp_id, LINE_YS[i])); sp_id += 1

    sps = '\n    '.join(shapes)
    return f'''<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<p:sld xmlns:a="http://schemas.openxmlformats.org/drawingml/2006/main"
       xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"
       xmlns:p="http://schemas.openxmlformats.org/presentationml/2006/main">
  <p:cSld><p:spTree>
    <p:nvGrpSpPr><p:cNvPr id="1" name=""/><p:cNvGrpSpPr/><p:nvPr/></p:nvGrpSpPr>
    <p:grpSpPr><a:xfrm><a:off x="0" y="0"/><a:ext cx="0" cy="0"/>
      <a:chOff x="0" y="0"/><a:chExt cx="0" cy="0"/></a:xfrm></p:grpSpPr>
    {sps}
  </p:spTree></p:cSld>
  <p:clrMapOvr><a:masterClrMapping/></p:clrMapOvr>
</p:sld>'''
``

### Usage

``python
# Set BRAND_FONT based on Step 0.5 font selection
BRAND_FONT = "Arial"  # or "Proxima Nova" if confirmed available

sections = [
    ("01", "From strategy to execution"),
    ("02", "The case for strategic continuity"),
    ("03", "Our role: where we lead, where we support"),
    ("04", "Workstream detail"),
    ("05", "Investment summary"),
    ("06", "How we work together"),
    ("07", "Next steps"),
]
xml = build_agenda_slide(sections)
with open('output-unpacked/ppt/slides/slide2.xml', 'w') as f:
    f.write(xml)
``

---

## Custom Slides — Readable Content Distribution (layouts 25, 27)

When a slide's content doesn't fit a standard layout, it still needs to be readable by default even though a designer will refine it later.

### Layout 25 Placeholder Map

| Placeholder | idx | Height | Use for |
|-------------|-----|--------|---------|
| Eyebrow | `idx=12` | 0.20" | Section label only — one short line |
| Title | `type=title` | 0.67" | Slide headline only |
| Body | `idx=11` | **4.98"** | All content — this is the entire working area |

**The body placeholder (`idx=11`) is the entire usable area.** Never put multi-line content in `idx=12` (0.20" — invisible).

### Readable Content Rules

- Body text: `sz=1100` (11pt) — fits ~25 lines in 4.98" at comfortable spacing
- Section headers within body: `sz=1000`, bold, color=`8888A1` — visual hierarchy without wasting space
- Dates, secondary labels: `sz=900`, color=`8888A1`
- Spacer paragraphs: `sz=600` between sections — breathing room without waste

### Python Helpers

``python
def esc(t):
    return t.replace('&','&amp;').replace('<','&lt;').replace('>','&gt;')

def p(text, bold=False, sz=1100, color=None):
    """Single paragraph. color is a hex string e.g. '8888A1', or None for white."""
    b = ' b="1"' if bold else ''
    fill = f'<a:solidFill><a:srgbClr val="{color}"/></a:solidFill>' if color else ''
    return (f'<a:p><a:r><a:rPr lang="en-US" sz="{sz}" dirty="0"{b}>'
            f'{fill}<a:latin typeface="{BRAND_FONT}"/>'
            f'</a:rPr><a:t>{esc(text)}</a:t></a:r></a:p>')

def spacer():
    """Thin blank line between content sections."""
    return '<a:p><a:endParaRPr lang="en-US" sz="600" dirty="0"/></a:p>'

def section_header(text):
    """Gray all-caps section label."""
    return p(text, bold=True, sz=1000, color='8888A1')
``

### `build_slide()` — Generic Placeholder Populator

Works for any layout — reads placeholder positions directly from the layout XML:

``python
import re

def build_slide(layout_num, eyebrow=None, title=None, body_paras=None):
    """
    eyebrow    → idx=12 (small strip at top — keep to one line)
    title      → type=title
    body_paras → idx=11 (main content area)
    Any slot left as None inherits the layout default.
    """
    content_map = {}
    if eyebrow:     content_map['12']    = eyebrow
    if title:       content_map['title'] = title
    if body_paras:  content_map['11']    = body_paras

    with open(f'output-unpacked/ppt/slideLayouts/slideLayout{layout_num}.xml') as f:
        layout = f.read()

    sp_blocks = re.findall(r'<p:sp\b.*?</p:sp>', layout, re.DOTALL)
    slides_sps = []
    sp_id = 2

    for sp in sp_blocks:
        if '<p:ph' not in sp:
            continue
        ph_type_m = re.search(r'<p:ph\b[^>]*type="([^"]+)"', sp)
        ph_idx_m  = re.search(r'<p:ph\b[^>]*idx="(\d+)"', sp)
        ph_type = ph_type_m.group(1) if ph_type_m else 'body'
        ph_idx  = ph_idx_m.group(1)  if ph_idx_m  else None
        key = 'title' if ph_type == 'title' else (ph_idx if ph_idx else 'body')

        sp_out = re.sub(r'(<p:cNvPr\s+id=")[^"]*(")', rf'\g<1>{sp_id}\2', sp, count=1)
        sp_id += 1

        if key in content_map:
            sp_out = re.sub(
                r'<p:txBody>.*?</p:txBody>',
                f'<p:txBody><a:bodyPr/><a:lstStyle/>{content_map[key]}</p:txBody>',
                sp_out, flags=re.DOTALL
            )
        slides_sps.append(sp_out)

    sps_xml = '\n    '.join(slides_sps)
    return f'''<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<p:sld xmlns:a="http://schemas.openxmlformats.org/drawingml/2006/main"
       xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"
       xmlns:p="http://schemas.openxmlformats.org/presentationml/2006/main">
  <p:cSld><p:spTree>
    <p:nvGrpSpPr><p:cNvPr id="1" name=""/><p:cNvGrpSpPr/><p:nvPr/></p:nvGrpSpPr>
    <p:grpSpPr><a:xfrm><a:off x="0" y="0"/><a:ext cx="0" cy="0"/>
      <a:chOff x="0" y="0"/><a:chExt cx="0" cy="0"/></a:xfrm></p:grpSpPr>
    {sps_xml}
  </p:spTree></p:cSld>
  <p:clrMapOvr><a:masterClrMapping/></p:clrMapOvr>
</p:sld>'''
``

### Usage Example

``python
# Set BRAND_FONT based on Step 0.5 font selection
BRAND_FONT = "Arial"  # or "Proxima Nova" if confirmed available

body = (
    section_header('SECTION ONE') +
    p('First point of content at normal body size.') +
    p('Second point of content.') +
    spacer() +
    section_header('SECTION TWO') +
    p('More content here.') +
    p('Additional detail.', sz=900, color='8888A1')
)

xml = build_slide(25,
    eyebrow    = p('EYEBROW LABEL', bold=True, sz=900),
    title      = p('Slide headline here', sz=2400),
    body_paras = body
)
with open('output-unpacked/ppt/slides/slideN.xml', 'w') as f:
    f.write(xml)
``
