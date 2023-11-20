---
title: Text justification
description: Learn about text justification and the different types of alignment options.
ms.date: 10/31/2023
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:11/10/2023
---

# Text justification

Alignment refers to how the text aligns with the margins of an object, for example, a page, a column, or a table cell. Typesetting programs, such as Microsoft Word, typically offer four types of alignment:

- Align Left: content is aligned with the left margin
- Align Right: content is aligned with the right margin
- Center: content is centered between the left and right margins
- Justify: content is distributed evenly between the left and right margins

For example, in a paragraph that is left-aligned, the left edge of the paragraph is flush with the left margin. The length of each line is determined by the number of words that can fit between the left and right margins, using the [line- and word-breaking](line-and-word-breaking.md) rules of the writing system. Frequently, the right edge of the left-aligned paragraph appears uneven, or *ragged*.

In a paragraph that is centered, both the left and right edges of each line of text is ragged.

In a paragraph that is justified, the left-most character is aligned with the left margin and the right-most character is aligned with the right margin. This process involves adjusting the letter spacing and word spacing to optimize the number of characters that fit on the line, while meeting the left and right margin constraints. The last line of a justified block of text might use left or right alignment rather than using significant amounts of whitespace to justify the line. [Hyphenation](line-and-word-breaking.md#hyphenation) can help reduce the amount of whitespace added between letters and words when justifying text.

Writing systems have rules for how text is justified. Rendering engines and fonts have various strategies for how justification rules are implemented. These strategies include:

- Inter-word/inter-cluster: whitespace between words or clusters (for example, Thai) is increased.
- Inter-word and inter-letter: both inter-word and inter-letter spacing can be expanded or reduced. This strategy isn't applicable for scripts that use baseline connectors (for example, Devanagari script) or fixed-width characters (for example, CJK ideographs). Connected glyphs shouldn't be separated for inter-letter spacing adjustments.
- Inter-ideograph: this strategy is like the inter-word strategy; however, spaces can be inserted between CJK ideographs. Spaces aren't inserted between characters of other scripts like Latin.
- Character elongation ad compression: Kashida is character elongation used in Arabic script to increase the length of the line connecting characters. It doesn't affect the sound or the meaning of the word, just the appearance. ARABIC TATWEEL (U+0640) is the character that represents this elongation. Microsoft Word allows for extra control over justification, with options for **Justify Low**, **Justify Medium**, and **Justify High**. When used with text written in Arabic script, **Justify High** uses wider kashidas than Justify Low.

Writing systems might use combinations of these strategies, especially if multiple scripts are used. For example, even though the Japanese writing system doesn’t use spaces between words, spacing can be adjusted around punctuation, script-change boundaries, and between characters.
