---
name: editing-gsma-crs
description: >-
  Generates, edits, and repairs GSMA Change Request (CR) Microsoft Word (.docx)
  documents with native OOXML Track Changes (<w:ins> and <w:del>), intact cover
  sheet table styling, clean step numbering, and valid ECMA-376 XML namespace
  declarations. Use when creating a GSMA CR from a template and baseline
  specification, applying redline revisions to a .docx CR, fixing broken step
  or list numbering in Word CRs, or resolving "Word found unreadable content"
  prompts in generated .docx files. Don't use for Google Docs native editing or
  plain Markdown changelogs.
---

# Editing GSMA Change Requests (.docx)

Create, edit, and repair GSMA Change Request (CR) `.docx` files by manipulating
Office Open XML (OOXML / ECMA-376) archives directly so headers, logos, table
styles, and native Word Track Changes remain intact.

## Workflow Overview

1. **Gather required inputs** (ask the editor for the Track Changes author name)
2. **Extract the `.docx` archive** and baseline specification text
3. **Populate or update the GSMA CR cover table** (`<w:tbl>`)
4. **Apply native OOXML Track Changes** (`<w:ins>` and `<w:del>`)
5. **Clean up step and list numbering** (`<w:numPr>` / inline step revisions)
6. **Preserve `<w:document>` XML namespaces** (`mc:Ignorable` compliance)
7. **Repackage and verify** the `.docx` archive

---

## 1. Gather Required Inputs (Ask for Editor Name)

Before generating or modifying any `<w:ins>` or `<w:del>` revision markup,
**ask the user what author name to use** for the change marks (for example,
`Jane Doe (Company)`).

- Never hardcode a default author name in scripts or XML templates.
- Use the provided `{author_name}` consistently in:
  - Every `<w:ins w:author="{author_name}" ...>` element
  - Every `<w:del w:author="{author_name}" ...>` element
  - The **Input Editor** row of the GSMA CR cover sheet table (when creating or
    updating the cover sheet)

Confirm which files are in scope:
- **Creating a new CR**: Requires the binary `.docx` CR template (e.g.,
  `Change Request Template.docx`) and the baseline specification `.docx` to
  extract verbatim existing text.
- **Editing or repairing an existing CR**: Requires the target CR `.docx` file
  (and optionally the baseline specification `.docx` if restoring accidentally
  altered baseline text).

---

## 2. Extract the `.docx` Archive & Baseline Text

A `.docx` file is a ZIP archive containing XML parts (`word/document.xml`,
`word/styles.xml`, `word/numbering.xml`, `word/header1.xml`, `word/media/*`,
`[Content_Types].xml`, `_rels/.rels`). Never generate a `.docx` from scratch,
as doing so strips the GSMA header, logo, table borders, fonts, and styles.

1. **Unpack the binary `.docx`** into a temporary working directory using
   Python's `zipfile` module (or read its entries into memory).
2. **Extract verbatim baseline text**: When creating or updating CR sections
   against a baseline specification `.docx`, parse the baseline's
   `word/document.xml` and extract the exact text of the affected sections
   character-for-character. Any deleted (`<w:del>`) or unchanged context text in
   the CR must match the baseline specification exactly.

---

## 3. Populate the GSMA Cover Table (`<w:tbl>`)

The GSMA CR cover sheet is the first `<w:tbl>` inside `<w:body>` (containing
rows for Change Request Title, Date, Meeting Number, Specification Number,
Current Version, Input Editor, Reasons/Benefits, Affected Entities, Status,
etc.).

When updating cover table cells (`<w:tc>`):
- **Preserve structure and formatting**: Keep existing cell properties
  (`<w:tcPr>` — shading, borders, widths), paragraph properties (`<w:pPr>`),
  and run formatting (`<w:rPr>` — font family, size, bold/italic).
- **Replace only text payloads**: Replace placeholder `<w:t>[...]</w:t>` strings
  inside the first run while removing redundant trailing runs in that paragraph.
- **Line breaks**: Convert newline breaks (`\n`) into native Word `<w:br/>`
  elements inside the run rather than inserting raw newline characters inside
  `<w:t>`.

---

## 4. Generate Native MS Word Track Changes (`<w:ins>` and `<w:del>`)

Never simulate redlines using colored font or strikethrough formatting
(`<w:strike/>` / `<w:color/>`), because specification editors cannot "Accept"
or "Reject" formatting-only redlines in Microsoft Word. Always generate real
OOXML Revision Markup inside each `<w:p>`:

| Change Type | OOXML Element | Inner Text Tag | Example |
| :--- | :--- | :--- | :--- |
| **Unchanged context** | `<w:r>` | `<w:t xml:space="preserve">` | `<w:r><w:t xml:space="preserve">Host: </w:t></w:r>` |
| **Deletion** | `<w:del>` | `<w:delText xml:space="preserve">` | `<w:del w:id="{id}" w:author="{author_name}" w:date="{iso_date}"><w:r><w:delText xml:space="preserve">old.example.com</w:delText></w:r></w:del>` |
| **Insertion** | `<w:ins>` | `<w:t xml:space="preserve">` | `<w:ins w:id="{id}" w:author="{author_name}" w:date="{iso_date}"><w:r><w:t xml:space="preserve">new.example.com</w:t></w:r></w:ins>` |

### Critical Track Changes Rules

1. **Use `<w:delText>` inside `<w:del>`**: OpenXML strictly requires
   `<w:delText>` (never `<w:t>`) inside `<w:del>`. Using `<w:t>` inside
   `<w:del>` causes text to render as normal undeleted text or triggers schema
   validation errors.
2. **Use `xml:space="preserve"`**: Include `xml:space="preserve"` on every
   `<w:t>` and `<w:delText>` that has leading or trailing spaces so Word does
   not collapse whitespace between adjacent runs and inline revisions.
3. **Minimal inline diffs**: Keep unchanged surrounding text in standard `<w:r>`
   runs and wrap only the modified tokens/phrases in `<w:del>` and `<w:ins>` so
   changes render as clean inline revisions rather than full-paragraph
   replacements.
4. **Unique `w:id` attributes**: Assign a unique, monotonically increasing
   integer `w:id` to every `<w:ins>`, `<w:del>`, `<w:pPrChange>`, or
   `<w:rPrChange>` across `word/document.xml` (start above the maximum existing
   `w:id` in the document).
5. **ISO-8601 timestamps**: Format `w:date` as `YYYY-MM-DDTHH:MM:SSZ` (e.g.,
   `2026-10-01T12:00:00Z`).

---

## 5. Clean Up Step and List Numbering

Word frequently corrupts step numbering in Change Requests when paragraphs are
copied from a baseline specification or when steps are inserted/deleted mid-list
(resulting in duplicate step numbers, restarts at 1, or continuation from a
previous section's list).

### Diagnosing Broken Numbering

Inspect each step paragraph's `<w:pPr>` in `word/document.xml`:
- **Automatic numbering (`<w:numPr>`)**: Paragraphs containing
  `<w:numPr><w:ilvl w:val="{level}"/><w:numId w:val="{num_id}"/></w:numPr>`
  derive their numbers from `word/numbering.xml`.
  - Discontinuous numbering happens when adjacent steps reference different
    `w:numId` values, wrong `w:ilvl` indentation levels, or when deleted
    paragraphs still carry active `<w:numPr>` without `<w:del/>` inside
    `<w:pPr><w:rPr>`.
- **Hardcoded / mixed numbering**: Occurs when some steps use `<w:numPr>` and
  others have literal text numbers (`"1. "`, `"Step 1:"`) inside `<w:t>`.

### Fixing Step Numbering

Choose the pattern that matches the baseline specification's style:

1. **When steps use automatic Word numbering (`<w:numPr>`)**:
   - Assign all steps in the same contiguous procedure to a single shared
     `w:numId` and consistent `w:ilvl` (e.g., `0` for top-level steps, `1` for
     sub-steps).
   - If a procedure starts at a number other than 1 (because it shares a
     `w:numId` with an earlier procedure), either define a dedicated `<w:num>`
     entry in `word/numbering.xml` pointing to the same `<w:abstractNumId>` with
     `<w:lvlOverride w:ilvl="0"><w:startOverride w:val="1"/></w:lvlOverride>`,
     or switch to explicit inline step numbering if the CR only excerpts a subset
     of steps.
   - When deleting an entire numbered paragraph under Track Changes, mark the
     paragraph mark itself as deleted by adding `<w:rPr><w:del w:id="{id}"
     w:author="{author_name}" w:date="{iso_date}"/></w:rPr>` inside `<w:pPr>`.
     Without `<w:del>` inside `<w:pPr><w:rPr>`, Word keeps counting the deleted
     paragraph in the list sequence.

2. **When steps use explicit text numbers (e.g., `1.`, `Step 1:`) or excerpted
   specification steps**:
   - Strip conflicting `<w:numPr>` tags from `<w:pPr>` so Word does not render
     a second automatic number next to the literal step number.
   - When inserting or deleting a step causes subsequent steps to renumber,
     represent the step number change explicitly with Track Changes so editors
     can see and accept the renumbering:
     ```xml
     <w:del w:id="101" w:author="{author_name}" w:date="{iso_date}">
       <w:r><w:delText xml:space="preserve">4. </w:delText></w:r>
     </w:del>
     <w:ins w:id="102" w:author="{author_name}" w:date="{iso_date}">
       <w:r><w:t xml:space="preserve">5. </w:t></w:r>
     </w:ins>
     ```

---

## 6. Prevent "Word Found Unreadable Content" (Root Namespace Integrity)

### Why the Error Happens

A Word `.docx` template's root `<w:document>` tag declares ~35 XML namespaces
(`xmlns:w`, `xmlns:mc`, `xmlns:w14`, `xmlns:w15`, `xmlns:w16se`, `xmlns:w16cid`,
`xmlns:w16`, `xmlns:w16cex`, `xmlns:w16sdtdh`, `xmlns:wp14`, etc.) along with
the OpenXML Markup Compatibility attribute:

```xml
mc:Ignorable="w14 w15 w16se w16cid w16 w16cex w16sdtdh wp14"
```

When serializing with Python's `xml.etree.ElementTree`:
1. Unregistered prefixes (`mc`, `w14`, `wp14`) are renamed to `ns0`, `ns1`, etc.
2. Namespace declarations not directly referenced by an element/attribute in the
   tree (`xmlns:w15`, `xmlns:w16se`, `xmlns:w16cid`, `xmlns:w16`, `xmlns:w16cex`,
   `xmlns:w16sdtdh`) are stripped from `<w:document>`, while
   `mc:Ignorable="w14 w15 w16se w16cid w16 w16cex w16sdtdh wp14"` remains on the
   root element.

Per **ECMA-376 Part 3 (Markup Compatibility, §10.1.1)**, every prefix listed in
`mc:Ignorable` must have a matching `xmlns:<prefix>` declaration in scope on
that element. If any prefix in `mc:Ignorable` is undeclared, MS Word flags the
file with *"Word found unreadable content"*.

### Required Fix When Serializing `word/document.xml`

Always preserve the original `<w:document ...>` opening tag and all namespace
prefixes from the source `.docx`:

```python
import re
import xml.etree.ElementTree as ET

# 1. Extract the exact opening <w:document ...> tag from the original XML bytes
orig_xml_str = orig_document_xml_bytes.decode("utf-8")
root_open_match = re.search(r"<w:document\b[^>]*>", orig_xml_str)
orig_root_open_tag = root_open_match.group(0)

# 2. Register every xmlns:<prefix>="URI" declared on the original root tag
for prefix, uri in re.findall(r'xmlns:([a-zA-Z0-9_]+)="([^"]+)"', orig_root_open_tag):
    ET.register_namespace(prefix, uri)

# 3. Parse, modify <w:body> (preserving the trailing <w:sectPr>), and serialize
root = ET.fromstring(orig_document_xml_bytes)
# ... apply edits to root ...
serialized_body = ET.tostring(root, encoding="unicode")

# 4. Replace the ElementTree-generated <w:document ...> opening tag with the
#    verbatim original opening tag so all mc:Ignorable xmlns declarations remain
patched_xml = re.sub(
    r"^<w:document\b[^>]*>",
    lambda _: orig_root_open_tag,
    serialized_body,
    count=1,
)
final_xml_bytes = (
    '<?xml version="1.0" encoding="UTF-8" standalone="yes"?>\r\n'.encode("utf-8")
    + patched_xml.encode("utf-8")
)
```

Also ensure:
- The original `<w:sectPr>` (page margins, headers/footers, and orientation) is
  preserved as the last child of `<w:body>`.
- All other ZIP archive members (`word/styles.xml`, `word/numbering.xml`,
  `word/header*.xml`, `word/media/*`, `[Content_Types].xml`, `_rels/*`) are
  copied into the output `.docx` archive untouched unless intentionally edited.

---

## 7. Verification Checklist

Run these automated checks on the generated `.docx` before delivering it:

- [ ] **Author check**: Confirm every new `<w:ins>` and `<w:del>` uses the
      editor-supplied `{author_name}` and no hardcoded placeholder names remain.
- [ ] **`mc:Ignorable` check**: Parse the opening `<w:document ...>` tag and
      verify that every space-separated prefix in `mc:Ignorable="..."` has a
      corresponding `xmlns:<prefix>="..."` attribute on `<w:document>`.
- [ ] **Track Changes tag check**:
      - Every `<w:del>` contains `<w:delText>` and zero `<w:t>` elements.
      - Every `<w:ins>` contains `<w:t>` and zero `<w:delText>` elements.
      - Every `w:id` on `<w:ins>` and `<w:del>` is unique.
- [ ] **Step numbering check**: Verify that sequential steps in each modified
      procedure increment continuously (`1, 2, 3, ...`) when Track Changes are
      viewed in "All Markup" and "Simple Markup" (accepted state).
