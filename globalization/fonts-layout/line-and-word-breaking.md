---
title: Line and word breaking
description: A global application must handle line and word boundaries for global data.
ms.date: 01/01/2022
---

# Line and word breaking

When a section of text is too long to be displayed as a single line, the text will need to be separated into multiple lines (line breaks) so that the text can fit within the available limits of the page, cell, or other display area. Typically, line breaks happen at the boundaries of words or syllables, or around punctuation. Each language has different rules for when line breaks can occur, which might be dependent on appearance, grammatical rules, or dictionary spelling.

A [writing system](writing-systems.md) is the combination of script and the rules that define how verbal communication should be represented. Many writing systems use characters like spaces as word dividers. Other word dividers include the ETHIOPIC WORDSPACE (፡ U+1361) and the Latin interpunct (MIDDLE DOT · U+00B7). For these writing systems, line breaking can occur at the word boundaries delineated by the word dividers.

Several languages and their writing systems do not use characters for word boundaries, including Chinese, Japanese, and Thai. Line breaking rules for these writing systems can be significantly more complex. For example, in Thai and Khmer, line breaking is based on grammatical analysis and on word matching in dictionaries when text is rendered.

## Punctuation

For most writing systems, there are rules about whether punctuation characters can appear at the start or at the end of a line. For example, for periods or commas, line breaking can occur after the punctuation; however, a line break should not occur between an opening quotation mark and the first word in the quotation. Rules for line breaking can be specified by national or organizational bodies, such as the Académie Française or The Chicago Manual of Style.

### Overriding default behavior for the space character

Instead of using the default (breaking) space character (U+0020), you can use any one of several non-breaking spaces to prevent line breaking at that position. These include:

- NO-BREAK SPACE (U+00A0)
- NARROW NO-BREAK SPACE (U+202F)
- WORD JOINER (U+2060)

As French requires a space before most punctuation, non-breaking spaces are often used to keep punctuation from wrapping incorrectly at line breaks.

### Hyphenation

In English, hyphens can be used to join words, for example, in compound modifiers like “large-scale development”. Hyphens can also be used to separate words; if you want to justify text to span the full width of a page, hyphens (HYPHEN-MINUS U+002D) can be inserted between syllables of words allowing for line breaking after the hyphen.

Several Microsoft products, including Microsoft Word, support automatic hyphenation. This feature allows the product to insert hyphens and line breaking to improve the appearance of your document.

Like the behavior of non-breaking spaces, the non-breaking hyphen (U+2011) can be used where you want a hyphenated word not to break across lines at the hyphen. 

For more information about hyphenations see [Proofing tools](../locale/dictionaries-spelling.md).

## Language and script specific rules

Writing systems can take one of three approaches when wrapping lines: between words, between syllables, and between characters. Writing systems can also define separation between words or syllables. For example:

- English is written using the Latin script, with spaces separating words, and line breaks can occur between words.
- Vietnamese is also written using the Latin script, but spaces separate syllables rather than words. Line breaking can occur between syllables.
- Khmer, Lao, and Thai do not separate words or syllables with a character like a space, but line breaks should only occur between words. Different strategies can be used to determine word boundaries, including rules-based, dictionary lookup, or statistical analysis (machine learning).
- Japanese is written using several scripts (Kanji, Hiragana, Katakana, Romaji). Japanese has a set of rules called Kinsoku Shori, specified in JIS X 4051, that describe which characters can appear at the beginning and end of lines, and which characters cannot be separated across lines.
- In abugidas like Javanese, multiple consonants (consonant clusters) can be combined, also known as stacking. Stacking can occur across word and syllable boundaries, and stacks are not split when breaking lines. In other words, line breaking occurs at the boundaries of “orthographic syllables” rather than “phonetic syllables”.

The World Wide Web Consortium (W3C) has published [an article](https://www.w3.org/International/articles/typography/linebreak) summarizing various typographic strategies for wrapping, and examples of the writing systems that use these strategies.
