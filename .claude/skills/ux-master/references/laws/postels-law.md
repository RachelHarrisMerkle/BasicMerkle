# Postel's Law

UX Theory card. Also called: The Robustness Principle. Audit lens: Input and recovery.

Related cards in the deck: [Tesler's Law](teslers-law.md), [Flow](flow.md).

## In one line

Be liberal in what you accept and conservative in what you send.

## What it asks of an interface

- People will enter information in many forms. Accept the variation and convert it to what the system needs.
- Expect a wide range of inputs, devices, abilities and connection quality, and keep working across them.
- The more situations a design anticipates, the more resilient it is.
- On the output side, be consistent and predictable: show data in one clear format and follow standards.

## When it applies

- Form inputs, search, file upload, import, URL handling, anything that parses what people give it.
- Layouts that must cope with long text, large type, small screens, slow networks and assistive technology.

## Detect a violation

**In code**

- Validation that rejects input the system could normalize: spaces or dashes in phone and card numbers, leading or trailing whitespace, uppercase in emails, a missing `https://` on a URL, a currency symbol or thousands separator in an amount, lowercase postal codes.
- Strict `pattern` attributes or regular expressions on names, phone numbers, addresses or postal codes. Names in particular must accept apostrophes, hyphens, spaces, non-Latin letters and single-word names.
- Date fields that demand one typed format with no picker and no tolerance for alternatives.
- `maxlength` that silently cuts off pasted content.
- Search with exact-match only: no trimming, no case folding, no tolerance for a small typo.
- File inputs that reject common formats or large files with no explanation and no stated limit.
- Layouts that break with long names, long words, translated strings or zoomed text: fixed widths and heights on text containers, truncation with no way to read the full value.
- On the sending side: the same data shown in different formats on different screens (dates, currency, units).

**In a screenshot or design file**

- Format instructions that do the system's work ("Enter numbers only, no spaces").
- Fields sized for one expected length.
- Designs shown only with short, tidy sample data.

## Example

**Bad:** A phone field that rejects "+1 (415) 555-0100" with "Invalid phone number" because it contains spaces and brackets.

**Good:** The field accepts any common format, strips the punctuation, stores the normalized number and shows it back in one consistent format.

## When laws conflict

- Against Constraints: constrain the choice when the valid set is known (a date picker, a select). Be liberal with format when people type freely. Both can be true on the same form.
- Against security and data quality rules: accept and normalize what is unambiguous. Reject only what you cannot interpret safely, and say exactly what to change.
- Against Pareto Principle: the common case does not excuse failing the uncommon one for input.

## Origin

Internet pioneer Jon Postel wrote the principle into the 1980 specification of TCP: implementations should be conservative in what they do and liberal in what they accept from others. It is also known as the robustness principle, and it carries over to interfaces as tolerance for human input.

Cite as: Jon Postel, the TCP specification (RFC 761, 1980).
