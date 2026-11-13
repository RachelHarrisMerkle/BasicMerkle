# Medium guide: Figma frames, wireframes, mockups and screenshots

Static work is judged before it can be used, so the review has to imagine the behaviour. Most real problems in static design are things that are not on the canvas.

**Brand:** apply the regime that matches where the design will ship (`../brand/README.md`). In a review, check fonts, tokens or palette, logo use and icon system as well as the laws; a design that reads well but uses the wrong regime is a finding.

## What you can and cannot verify

- From an image you can judge hierarchy, grouping, consistency, labels, contrast and counts. You can only estimate sizes. Mark every size you estimated "(est.)".
- From a Figma frame read through Figma's tools you can measure sizes, spacing and layer structure exactly. Follow `../figma/figma-setup.md` and `../figma/audit-method.md`, and keep to the call budget they describe.
- You cannot verify real response time, real content length, behaviour on interaction or how people actually use it. Say so under "Not checked" and name the method that would settle it (`../methods/usability-test.md`).

## What static work usually forgets

These are findings by absence. For each, say where you looked.

- **States:** hover, visible focus, pressed, disabled, loading, error, success, empty. A design with only the happy state is half a design.
- **Real content:** the longest name, the empty list, a two-line error, a number with seven digits, another language. Lorem ipsum hides overflow and hierarchy problems.
- **Other sizes:** the same screen at phone width and at a wide desktop.
- **Transitions:** what happens between two frames, and how long the person waits.
- **Edge paths:** back, cancel, undo, timeout, offline.
- **Handoff notes:** which element is the primary action, what each icon does, which values are tokens, what the designer decided on purpose.

## Wireframes

Judge structure, not finish: hierarchy, grouping, labels, the primary action, the number of choices, the order of content. Do not critique colour or type in a grey wireframe, and do not let polish creep in before the structure is settled (Aesthetic-Usability Effect).

## When you are asked to produce a design

Write the UX read first (`../modes/build.md`), then design the states alongside the happy path, not after. Annotate the primary action and the laws that set constraints on the frame so the reviewer can check them.
