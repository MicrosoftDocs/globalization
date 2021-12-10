---
title: Page or text alignment
description: In typesetting and page layout, alignment is the setting of text flow or image placement relative to a page, column (measure), table cell or tab. 
ms.assetid: 6b1de8ff-d50c-4b36-bd97-e3e7eda36406
ms.date: 05/01/2017
---
# Page or text alignment

In typesetting and page layout, alignment is the setting of text flow or image placement relative to a page, column (measure), table cell or tab.
Type alignment sometimes referred to as “text alignment”, “text justification”, “type justification”, or “document direction.”
Additionally, this may be referred to as _reading order_.
Reading order describes the order in which a block of text is displayed, sometimes in contrast with how the text is entered or stored, which is normally in logical order.

To describe how a text flows into lines, one needs to answer three questions:

- Which way does the text flow within a line (what is the text direction or alignment)?
- Which way do the lines stack (what is the block progression)?
- Which way do the glyphs face (what is the glyph orientation: i.e. do the glyphs need to be rotated if the flow changes)?

Chinese may be written either horizontally (read left-to-right, then top-to-bottom as English is) or vertically (read top-to-bottom, then right-to-left), sometimes in the same document!
This is called a bi-orientational script; see the table below for examples of each orientation.
Other East Asian languages such as Japanese (Kanji) and Yi also have the same text alignment.

| CSS | Text direction and progression | Language | Source | Example |
| --- | --- | --- | --- | --- |
| \[default\] | Left-to-right directionality in horizontal text. No inherent directionality in vertical text. | Armenian | Universal Declaration of Human Rights, United Nations | Քանզի մարդկային ընտանիքի բոլոր անդամներին ներհատուկ արժանապատվությունըև հավասար ու անօտարելի իրավունքները աշխարհի ազատության, արդարության ու խաղաղության հիմքն են.|
| `direction: rtl;` | Right-to-left directionality in horizontal text. No inherent directionality in vertical text. | Hebrew | Universal Declaration of Human Rights, United Nations | <span lang="he" dir="rtl">הואיל והכרה בכבוד הטבעי אשר לכל בני משפהת האדם ובזכויותיהם השוות והבלתי נפקעות הוא יסוד החופש, הצדק והשלום בעולם.</span> |
|`writing-mode: vertical-lr;` | Top to bottom directionality in vertical text. No inherent directionality in horizontal text. | Traditional Mongolian | I. J. Schmidt Grammatik der mongolischen Sprache; St. Petersburg, 1831 | ![Traditional Mongolian Script](./images/Mongolian.JPG "Traditional Mongolian Script") |
|`writing-mode: vertical-rl;` | Left to right directionality in horizontal text. Top to bottom directionality in vertical text.| Chinese | Universal Declaration of Human Rights, United Nations | ![Traditional Chinese Script](./images/TradChineseDir.jpg "Traditional Chinese Script") |
|`writing-mode: vertical-rl; transform: rotate(180deg);` | Left to right directionality in horizontal text. Bottom to top directionality in vertical text. | Hanunó’o script | Conklin, Harold. 1953. Hanunoo-English Vocabulary. Berkeley: University of California Press. \[University of California Publications in Linguistics 9:1-290\] | ![Hanunó’o Script](./images/Hanunoo.jpg "Hanunó’o Script") |

The following are general context rules for the reading order and alignment of text:

- If the first strong character is left to right, reading order will be left to right and text will be left aligned.

- If the first strong character is right to left, reading order will be right to left and text will be right aligned.

- If only neutral characters are typed, the reading order and the alignment will follow the paragraph direction (can be left to right, or right to left) until the first strong character is typed.

Any time you change the first strong character from a left-to-right language to a right-to-left language, and vice versa, the reading order and the alignment change accordingly.

The text direction and cultural expectations can impact other features.
For example, lines with Japanese or Korean text will have the underline appear on the right, while Chinese (Simplified and Traditional scripts) on the left.
The positions of punctuation marks, for example, the relative position of commas and full stops, differ between horizontal and vertical writing.
Punctuation such as parentheses, quotation marks, book title marks (Chinese), ellipsis mark, dash, wavy dash (Japanese), proper noun mark (Chinese), wavy book title mark (Chinese), emphasis mark, and cho-on mark (Japanese) are all rotated 90 degrees when switching between horizontal and vertical text.

![Underlined text in four scripts](./images/Underline_Text.png "Underlined text in four scripts")

**Figure 1:** Underlined text in four scripts.

[Ruby characters](overlay.md), which provide a phonetic guide for unusual or difficult- to-read characters, follow the direction of the main text.
Inserted text in the Roman alphabet is usually written horizontally, or turned sideways when it appears in vertical text, with the base of the characters on the left.

When a text is written in horizontal format, pages are read in the same order as English books, with the binding at the left and pages progressing to the right.
Vertical books are printed the other way around, with the binding at the right, and pages progressing to the left.

For bidirectional languages—such as Arabic and Hebrew, the text should be aligned to the right and the overall text direction is right-to-left.
A right-to-left document is characterized by the following:

- The default cursor position is on the right side.
- The default paragraph direction is right-aligned.
- Text flows from the right side to the left side.
- The default reading order is right-to-left.
- If they exist, column names and row names originate and increase from top-right corner leftwards and towards the bottom.
- If they exist, tabs originate from either the top-right or the bottom-right side and increase towards the left.
