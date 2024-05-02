---
title: Text alignment and pagination
description: Learn about text alignment and pagination in typesetting and page layout.
ms.date: 10/31/2023
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:11/10/2023
---
# Text alignment and pagination

In typesetting and page layout, alignment is the setting of text flow or image placement relative to a page, column (measure), table cell or tab. Alignment is dependent on the typeface, the font size, the length of the text area, the line-spacing (also called leading), the letter spacing (spacing between all letters), and kerning (spacing between specific pairs of letters).

Type alignment is sometimes referred to as “text alignment”, “text justification”, “type justification”, or “document direction.” Additionally, these terms might be referred to as "reading order". Reading order describes the order in which a block of text is displayed, sometimes in contrast with how the text is entered or stored, which is normally in logical order.

To describe how a text flows into lines, one needs to answer three questions:

- Which way does the text flow within a line (what is the text direction or alignment)?
- Which way do the lines stack (what is the block progression)?
- Which way do the glyphs face (what is the glyph orientation: that is, do the glyphs need to be rotated if the flow changes)?

For example, English, and other languages using the Latin script, are typically written from left-to-right, from top-to-bottom of the page. Chinese might be written either horizontally (left-to-right, top-to-bottom) or vertically (top-to-bottom, right-to-left). If both directions are present in the same document, it is called a bi-orientational script.

## Controlling orientation in HTML using CSS

There are three CSS properties that allow control over the direction of text within text flows:

- `direction` - specifies the text flow within a block-level element:
  - `ltr` (left to right)
  - `rtl` (right to left)
- `writing-mode` - specifies the order of the lines:
  - `horizontal-tb` (horizontal, from top to bottom)
  - `vertical-rl` (vertical, from right to left)
  - `vertical-lr` (vertical, from left to right)
- `text-orientation` – specifies the orientation of text within a line of vertical text:
  - `mixed` (characters from horizontal-only scripts are rotated 90° clockwise from their standard orientation, while characters from vertical scripts are displayed in their default orientation)
  - `upright` (all characters are displayed in their default orientation)
  - `sideways` (all characters are rotated 90° clockwise from their standard orientation)

In addition to these three properties, you can use the `unicode-bidi` property to manage the [directionality](text-directionality.md) of text segments, including embedded sequences, isolated sequences, and overrides.

You can obtain similar effects with the `rotate` and `transform` properties that you can obtain with `writing-mode`.

For more information about CSS Writing Modes Level 3, see [https://www.w3.org/TR/css-writing-modes-3/](https://www.w3.org/TR/css-writing-modes-3/)

## Comparison of different orientations

The following table shows examples of different orientations and directionality using translations of Article 1 of the Universal Declaration of Human Rights, published by The Office of the High Commissioner for Human Rights ([https://www.ohchr.org/](https://www.ohchr.org/)).

| CSS | Text direction and progression | Language | Example |
| --- | --- | --- | --- | --- |
| \[default\] | Text flows horizontally from left to right, from top to bottom. | English | All human beings are born free and equal in dignity and rights. They are endowed with reason and conscience and should act towards one another in a spirit of brotherhood. |
| `direction: rtl;` | Text flows horizontally from right to left, from top to bottom. | Hebrew | <iframe src="UDHR_he.html" width="100%" height="100%"></iframe> |
| `writing-mode: vertical-rl;` | Text flows vertically from top to bottom, from right to left. | Traditional Chinese | <iframe src="UDHR_zh-Hant.html" width="100%" height="100%"></iframe> |
| `writing-mode: vertical-lr;` | Text flows vertically from top to bottom, from left to right. The characters in the Mongolian script are rotated 90°.  | Mongolian | <iframe src="UDHR_mn-Mong.html" width="100%" height="100%"></iframe> |

## Bi-orientational scripts, punctuation, and text formatting

The text direction and cultural expectations can affect other features. For example, vertical lines with Japanese or Korean text have the underline appear on the right, while Chinese (Simplified and Traditional scripts) on the left. The positions of punctuation marks, for example, the relative position of commas and full stops, differ between horizontal and vertical writing. Punctuation such as parentheses, quotation marks, book title marks (Chinese), ellipsis mark, dash, wavy dash (Japanese), proper noun mark (Chinese), wavy book title mark (Chinese), emphasis mark, and cho-on mark (Japanese) are all rotated 90 degrees when switching between horizontal and vertical text. The following examples show translations of the Preamble of the Universal Declaration of Human Rights in horizontal and vertical writing modes.

Horizontal:
<iframe src="UDHR_horizontal.html" width="100%" height="270px"></iframe>

Vertical:
<iframe src="UDHR_vertical.html" width="100%" height="320px"></iframe>

## Directionality and book binding

When a text is written in horizontal format, pages are read in the same order as English books, with the binding at the left and pages progressing to the right. Binding for vertical books corresponds to the reading direction on the page. For example, for Japanese using vertical text, the binding is on the right and pages progressing to the left.
