# Approach A — Patch Workflow

Use when the deck is already close to on-brand, or when the user cannot provide the master template (fonts + colors only in that case).

**Limitation:** slide visual structure stays as-is. Divider and section header slides may still look structurally off after patching — use Approach B for those if needed.

---

## Step 1 — Unpack and Audit

``bash
python scripts/office/unpack.py input.pptx unpacked/
extract-text input.pptx
``

### Layout audit

``python
import xml.etree.ElementTree as ET, glob

layout_names = []
for slide_f in sorted(glob.glob('unpacked/ppt/slides/slide*.xml'),
                      key=lambda x: int(''.join(filter(str.isdigit, x.split('slide')[-1])))):
    rel_f = slide_f.replace('/slides/slide', '/slides/_rels/slide').replace('.xml','.xml.rels')
    for rel in ET.parse(rel_f).getroot():
        if 'slideLayout' in rel.get('Target',''):
            num = rel.get('Target').replace('../slideLayouts/slideLayout','').replace('.xml','')
            layout_f = f'unpacked/ppt/slideLayouts/slideLayout{num}.xml'
            csp = ET.parse(layout_f).getroot().find('.//{http://schemas.openxmlformats.org/presentationml/2006/main}cSld')
            name = csp.get('name') if csp is not None else 'unknown'
            layout_names.append(name)
            slide_num = ''.join(filter(str.isdigit, slide_f.split('slide')[-1]))
            print(f'Slide {slide_num}: layout{num} → {name}')

default_count = sum(1 for n in layout_names if n.upper() in ('DEFAULT', 'BLANK', 'OFFICE THEME'))
if default_count > len(layout_names) * 0.3:
    print(f'\n⚠️  {default_count}/{len(layout_names)} slides use a generic layout.')
    print('Switch to Approach B for full fidelity.')
``

### Theme check

``python
import xml.etree.ElementTree as ET, glob
for tf in glob.glob('unpacked/ppt/theme/theme*.xml'):
    root = ET.parse(tf).getroot()
    print(f'{tf}: theme name = "{root.get("name","")}"')
# If not "Merkle_2025_v2", the theme must be replaced — requires the master template file.
``

### Font audit

``python
import xml.etree.ElementTree as ET, glob
ns_a = 'http://schemas.openxmlformats.org/drawingml/2006/main'
for f in sorted(glob.glob('unpacked/ppt/slides/slide*.xml'),
                key=lambda x: int(x.split('slide')[-1].replace('.xml',''))):
    fonts = set()
    for rPr in ET.parse(f).getroot().iter(f'{{{ns_a}}}rPr'):
        latin = rPr.find(f'{{{ns_a}}}latin')
        if latin is not None:
            fonts.add(latin.get('typeface',''))
    if fonts - {'Proxima Nova', '+mj-lt', '+mn-lt', ''}:
        print(f'{f}: non-brand fonts: {fonts}')
``

---

## Step 2 — Install Merkle Theme from Template

**Requires the master template file.**

``bash
python scripts/office/unpack.py template.pptx template-unpacked/

# Replace theme XML
cp template-unpacked/ppt/theme/theme1.xml unpacked/ppt/theme/theme1.xml

# Copy slide master (contains logo, background geometry, footer placement)
cp template-unpacked/ppt/slideMasters/slideMaster1.xml unpacked/ppt/slideMasters/slideMaster1.xml
cp template-unpacked/ppt/slideMasters/_rels/slideMaster1.xml.rels \
   unpacked/ppt/slideMasters/_rels/slideMaster1.xml.rels

# Copy template media with tmpl_ prefix to avoid overwriting deck's own assets
for f in template-unpacked/ppt/media/*; do
    cp "$f" "unpacked/ppt/media/tmpl_$(basename $f)"
done

# Copy embedded fonts
mkdir -p unpacked/ppt/fonts
cp template-unpacked/ppt/fonts/font*.fntdata unpacked/ppt/fonts/ 2>/dev/null || true
``

Update `[Content_Types].xml` to register any new media and font file types copied in.

If the master template is **not available**, skip this step and note it in the Designer Review Summary.

---

## Step 3 — Apply Brand Fonts

The font to apply should already be confirmed from the Font Selection step (see `brand-guidelines.md`). Use the user's choice — or Arial if they skipped. If Proxima Nova was chosen, run the availability check before proceeding.

``python
import glob, re

BRAND_FONT = "Proxima Nova"  # replace with "Arial" if fallback applies
FONT_PATTERN = re.compile(r'(<a:latin\s[^>]*typeface=")[^"]*(")', re.DOTALL)

for f in (glob.glob('unpacked/ppt/slides/slide*.xml') +
          glob.glob('unpacked/ppt/slideLayouts/slideLayout*.xml') +
          glob.glob('unpacked/ppt/slideMasters/slideMaster*.xml')):
    with open(f) as fh:
        content = fh.read()
    new = FONT_PATTERN.sub(rf'\g<1>{BRAND_FONT}\2', content)
    if new != content:
        with open(f, 'w') as fh:
            fh.write(new)
``

---

## Step 4 — Remap Off-Brand Colors

``python
import glob, re

# Note: #333333 and #555555 are intentionally excluded — they appear as
# legitimate design colors in the Merkle agenda slide template (divider lines
# and row numbers). Remapping them would corrupt correctly-built agenda slides.
COLOR_MAP = {
    '1F2937': '040E4B', '0657D3': '0328D1', '0B1148': '040E4B',
    '2E4EAB': '031FA4', 'E03C31': 'DD3038', '6B7280': '8888A1',
    '888888': '8888A1', 'D1D5DB': 'D6D6DF',
    'E8E9EC': 'E5E5E9', '111111': '040E4B', '364153': '040E4B',
    '4A5568': '8888A1', '60607D': '8888A1',
    'AAAAAA': '8888A1', 'DDDDE6': 'D6D6DF', 'E4E4EC': 'E5E5E9',
    'EFF2FA': 'F2F2F4', 'F2F2F2': 'F2F2F4', 'F3F4F6': 'F2F2F4',
    'F4F4F7': 'F2F2F4', 'F5B840': '0391F2',
}

for f in glob.glob('unpacked/ppt/slides/slide*.xml'):
    with open(f) as fh:
        content = fh.read()
    for old, brand in COLOR_MAP.items():
        content = re.sub(old, brand, content, flags=re.IGNORECASE)
    with open(f, 'w') as fh:
        fh.write(content)
``

---

## Step 5 — Register Embedded Proxima Nova Fonts

The `.fntdata` files were copied from the template in Step 2. Now register them in `presentation.xml`:

``python
import re

with open('unpacked/ppt/_rels/presentation.xml.rels') as f:
    rels = f.read()

FONT_RELS = '''  <Relationship Id="rId_font1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/font" Target="fonts/font1.fntdata"/>
  <Relationship Id="rId_font2" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/font" Target="fonts/font2.fntdata"/>
  <Relationship Id="rId_font3" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/font" Target="fonts/font3.fntdata"/>
  <Relationship Id="rId_font4" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/font" Target="fonts/font4.fntdata"/>'''

if 'font1.fntdata' not in rels:
    rels = rels.replace('</Relationships>', FONT_RELS + '\n</Relationships>')
    with open('unpacked/ppt/_rels/presentation.xml.rels', 'w') as f:
        f.write(rels)

FONT_EMBED = """<p:embeddedFontLst>
  <p:embeddedFont>
    <p:font typeface="Proxima Nova" panose="020B0604020202020204" pitchFamily="34" charset="0"/>
    <p:regular r:id="rId_font1"/>
    <p:bold r:id="rId_font2"/>
    <p:italic r:id="rId_font3"/>
    <p:boldItalic r:id="rId_font4"/>
  </p:embeddedFont>
</p:embeddedFontLst>
"""

with open('unpacked/ppt/presentation.xml') as f:
    prs = f.read()

if 'embeddedFontLst' not in prs:
    # ⚠️ Must be placed BEFORE <p:defaultTextStyle> — schema order is strict
    prs = prs.replace('<p:defaultTextStyle>', FONT_EMBED + '<p:defaultTextStyle>')
    with open('unpacked/ppt/presentation.xml', 'w') as f:
        f.write(prs)
``

---

## Step 6 — Import Missing Layouts (if needed)

When the input deck is missing Merkle layouts, import them from the template:

1. Copy layout XMLs and rels from template
2. **⚠️ CRITICAL — prefix template media** to avoid overwriting deck's own media:
   ``bash
   for f in template-unpacked/ppt/media/*; do
     cp "$f" "unpacked/ppt/media/tmpl_$(basename $f)"
   done
   ``
3. Update layout rels to reference `tmpl_`-prefixed media:
   ``python
   import glob, re
   for f in glob.glob('unpacked/ppt/slideLayouts/_rels/*.rels'):
       with open(f) as fh: content = fh.read()
       new = re.sub(r'Target="\.\./media/(image[^"]+)"',
                    r'Target="../media/tmpl_\1"', content)
       if new != content:
           with open(f, 'w') as fh: fh.write(new)
   ``
4. **Strip decorative shapes from layouts** — layouts must contain only placeholder `<p:sp>` elements:
   ``python
   import glob, re
   def strip_decorative(xml):
       xml = re.sub(r'<p:bg\b[^>]*/>', '', xml)
       xml = re.sub(r'<p:bg\b.*?</p:bg>', '', xml, flags=re.DOTALL)
       xml = re.sub(r'<p:grpSp\b.*?</p:grpSp>', '', xml, flags=re.DOTALL)
       xml = re.sub(r'<p:pic\b.*?</p:pic>', '', xml, flags=re.DOTALL)
       xml = re.sub(r'<p:graphicFrame\b.*?</p:graphicFrame>', '', xml, flags=re.DOTALL)
       def keep_ph_only(m):
           return m.group(0) if '<p:ph' in m.group(0) else ''
       xml = re.sub(r'<p:sp\b.*?</p:sp>', keep_ph_only, xml, flags=re.DOTALL)
       return xml
   for f in glob.glob('unpacked/ppt/slideLayouts/slideLayout*.xml'):
       with open(f) as fh: content = fh.read()
       new = strip_decorative(content)
       if new != content:
           with open(f, 'w') as fh: fh.write(new)
   ``
5. Update slide master rels and `<p:sldLayoutIdLst>` to include all layouts
6. Register new layout files and `tmpl_` media in `[Content_Types].xml`
7. Re-point each slide's layout rel to the correct layout number

---

## Step 7 — Flag Custom Slides

For each custom slide (see brand-guidelines.md), inject a warning into its speaker notes:

``python
import re

FLAG_TEXT = "⚠️ DESIGNER REVIEW: Custom layout — verify fit and spacing."

# CUSTOM_SLIDES: dict of {slide_number: "one-line reason"}
CUSTOM_SLIDES = {
    4: "Complex multi-panel infographic — no standard template equivalent",
}

for slide_num, reason in CUSTOM_SLIDES.items():
    notes_path = f'unpacked/ppt/notesSlides/notesSlide{slide_num}.xml'
    with open(notes_path) as f:
        content = f.read()

    FLAG_PARA = f'''<a:p>
            <a:r>
              <a:rPr lang="en-US" dirty="0"/>
              <a:t>{FLAG_TEXT}</a:t>
            </a:r>
          </a:p>
          <a:p>
            <a:r>
              <a:rPr lang="en-US" dirty="0"/>
              <a:t>Reason: {reason}</a:t>
            </a:r>
          </a:p>'''

    new_content = re.sub(
        r'(<p:ph type="body"[^>]*/>[^<]*(?:<[^>]+>[^<]*)*?<a:lstStyle/>)',
        r'\1' + FLAG_PARA,
        content, count=1, flags=re.DOTALL
    )
    if new_content != content:
        with open(notes_path, 'w') as f:
            f.write(new_content)
        print(f"  Slide {slide_num}: flagged ✓")
    else:
        print(f"  Slide {slide_num}: COULD NOT FLAG — inspect notes XML manually")
``

---

## Step 8 — Pack

``bash
python scripts/clean.py unpacked/
python scripts/office/pack.py unpacked/ output.pptx --original input.pptx
``

---

## Common Issues

| Issue | Cause | Fix |
|-------|-------|-----|
| Slides garbled / double-background | Texture layout + slide's own bg shapes → double layer | Switch to plain structural layout |
| File opens with repair dialog | `ns0:`/`ns1:` namespace mangling from `ET.write()` | Redo XML edits using string/regex only — never `ET.write()` |
| `embeddedFontLst` validation error | Wrong position in `presentation.xml` | Place **before** `<p:defaultTextStyle>` |
| Off-brand colors throughout | Deck uses its own palette | Remap with color table in Step 4 |
| Proxima Nova not rendering | Fonts not embedded | Follow Steps 2 and 5 |
| Divider slides look structurally wrong | Approach A can't fix structural issues | Use Approach B for those slides |
| Leftover editorial note box | "DO NOT EDIT" text box in slide | Find `<p:sp>` with that text and remove the entire element |
| Placeholder `X`/`x` bullets | Unfilled template content | Remove `<a:p>` blocks whose combined `<a:t>` text is only `X` or `x` |
| File opens as template / extension error | Source was `.potx` | Replace `presentationml.template.main+xml` with `presentationml.presentation.main+xml` in `[Content_Types].xml` |
