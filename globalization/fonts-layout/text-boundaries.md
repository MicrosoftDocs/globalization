---
title: Text boundaries
description: Written languages have varying definitions and conventions for the boundaries that define word and line breaking.
ms.date: 10/31/2023
author: jowilco
---

# Text boundaries

Applications like Microsoft Word provide several features that require identifying text boundaries of the supported writing systems. For example:

- You can view document information like the number of characters, words, lines, or paragraphs.
- If you press Ctrl + right arrow, your cursor moves to the next word.
- If the text that you are entering extends past the margin, the text wraps to the next line.
- If you press F8 repeatedly, the selection will expand to the entire word, sentence, paragraph, section, and document.

## Character boundaries

Unicode supports features like combining characters and ligatures. When determining a count of characters, each character may comprise one or more Unicode code points. As discussed in [Text layout](text-layout.md), the words “Tiếng Việt” (“Vietnamese” in Vietnamese) contains the character ệ, which could comprise one of four combinations of Unicode code points. However, you expect that “Việt” contains 4 “characters”. Counting the number of characters in a document requires an understanding of where one character ends and where the next character starts.

## Word boundaries

While it is difficult to have a concise definition of the term “word” that applies to all languages, writing systems, and scripts, we can consider it to be a sequence of characters that have a specific meaning. Words are comprised of one or more morphemes and represent combinations of syllables. Writing systems like Latin and Arabic can use spaces to separate words. Vietnamese uses the Latin script, but spaces separate syllables rather than words. Writing systems used for other East Asian languages, such as Thai, Japanese, and Chinese, do not separate words or syllables with word separators like spaces.

Features like selecting the word or moving to the next word in the document require an understanding of word boundaries in the various writing systems. Rules for implementing word boundary identification might depend on the script used, dictionary lookup, or heuristics. In addition, within one language, differences in conventions or between style guides might require alternate interpretations of how to define word boundaries. See [Line and word breaking](line-and-word-breaking.md) for more details.

## Line-break boundaries

When displaying text that spans multiple lines, separate lines are a result of either a line breaking character (e.g., line feed U+000A) or because text has been automatically wrapped to fit within a predetermined boundary (e.g., page margins in a word processor).

Various algorithms exist to calculate the most appropriate line break location. Location for line breaks could include word boundaries, before or after specific characters, or be enabled using automatic hyphenation tools. See [Line and word breaking](line-and-word-breaking.md) for more details.

## Sentence boundaries

In English, several characters can indicate the end of a sentence, including the question mark, the exclamation mark, and the period. However, a period can also be used to indicate an abbreviation, as a decimal separator, and as a delimiter (e.g., web address). Like line-breaking, semantical analysis is often needed to determine whether a punctuation mark indicates the end of a sentence or is being used for a different purpose.

## Using locale-aware and language-aware methods for boundary detection

Both .NET and Java have classes that facilitate boundary detection. For Windows, you can use the [SelectableWordsSegmenter](/uwp/api/windows.data.text.selectablewordssegmenter) class, while Java and ICU provide the BreakIterator class.
