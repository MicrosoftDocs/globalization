---
title: Collation, sorting, and string comparison
description: In world-ready applications, the alphabetical order can vary among languages, and the conventions for sequencing items can also be quite different.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/10/2023

---

# Collation, sorting, and string comparison

Each language has a set or sets of rules for how language strings should be sorted or "collated" into an ordered list. Collation is the term for how the sorting order of strings of characters is determined. This concept is important to globalization when it comes to the alphabetic order of each language.

The sorting order for a given language can simply be the  Latin alphabetical order. English is one such language.  However, even within English, there are special cases such as hyphenated words where the sorting order can vary depending on which source you are reading. The Chicago Manual of Style specifies a different sort order than the Oxford English Dictionary. In other languages, the order can also be determined by official authorities or institutions. For example, the Royal Spanish Academy issued a new alphabetization rule in 1994, and the Swedish Academy made a change as recently as in 2006.

Sorting can even change within one language depending on the context. For example, in Germany phonebook ordering is different than dictionary ordering.

Whether it’s a human being or a computer doing the sorting, it is performed by comparing strings. When you are reading an encyclopedia, you are expecting that Copenhagen comes before copper. Sorting algorithms do the same thing, but adapt to the language and region when doing comparisons.

## User experience

Most users choose their sort order indirectly by setting their language in the operating system, browser, or application. If the chosen language has more than one sort order, the user may specify which of the available sort orders they prefer.

## Implementing sorting and string comparisons

There are several situations where you would want your sort order not to vary from culture to culture (for example, for maintaining ordered lists that require fast searching). This is known as culture-insensitive sorting.

Because each language sorts uniquely and sorting rules tend to be complex, implementing sorting correctly is difficult. Fortunately, platforms provide sorting functionality that applications can depend on.

## Notes on ordering

This section gives examples of language-specific conventions that affect sorting.

### Special letters, characters, and symbols

#### Combinations of letters

Until 1994, CH and LL were treated as single letters in Spanish. But after the Spanish Academy changed their ruling, CH is collated between CG and CI, and LL between LK and LM.

#### Characters with diacritics

A diacritic is a glyph (a typographical mark) added to a letter or to a basic glyph. Some diacritics are called accents. Characters with diacritics can be treated as distinct letters or equivalent to the unaccented letter.

For example, letters with umlaut are treated as the corresponding non-umlauted letters in German. However, in a German phonebook, umlauts are sorted as combinations of letters, because some German surnames appear in both forms, for example Müller and Mueller. In Arabic, Hamza, which is created diacritically, can be considered the 29th letter even though there are only 28 “full” letters. Some French dictionary ordering traditions use backward secondary sorting for accented letters, meaning they are sorted by the last accented letter in a word.

#### Equivalent letters

V and W are now treated as separate letters in Swedish, but before 2006 W was treated as a version of V. In German, ß is sorted as SS.

#### Accented letters

See [Characters with diacritics](#characters-with-diacritics).

#### Lowercase vs uppercase

In some cases, the sorting order might be affected by lowercase or uppercase letters. Many modern scripts, such as Latin, Greek, Cyrillic, and Armenian have case, but not all do. For a detailed explanation, refer to [Case mapping](../input/text-rendering.md#capitalization-upper-casing-and-lower-casing).

#### Punctuation, symbols and spaces

Punctuation, including spaces, and symbols such as the kashida in Arabic might affect the sorting order.

### Standards and normalization

#### Sorting standards

There are standards, national or otherwise, that define collation for a given language. For example, the Japanese Industrial Standards (JIS) include JIS X 4061:1996 which defines collation of Japanese character strings. Unicode is another standard, used with most writing systems in the world. It aims to define a code point for each written character, as well as some symbols, emojis, and control and formatting codes. A code point is a number instead of a visual glyph, making collation possible for computers. This way a given character is defined abstractly, leaving its visual representation to individual systems and applications. For various historical reasons, some basically identical characters do have multiple code points, however.

#### Normalization

Some Unicode characters have multiple equivalent binary representations consisting of sets of combining and/or composite Unicode characters. The Unicode standard defines a process called normalization that returns one binary representation when given any of the equivalent binary representations of a character. For example, the latin small letter a with diaeresis (umlaut) might be represented by either the character ä (U+00E4) or a (U+0041) with the combining diaeresis character ¨ (U+0308).

<!-- For a detailed explanation, refer to [String normalization](../text/text-normalization.md). -->

## Market-specific sorting examples

East Asian languages, such as Chinese and Japanese, can be sorted by either pronunciation or stroke count. For example, Chinese dictionaries are traditionally sorted by radical, and then the number of pen strokes in the character. A radical is a base component of a complex character, typically with pictographic or ideographic origins.

For sorting Japanese names, some software features have phonetic name support, such as the Japanese Outlook Address Book.

Simplified Chinese generally uses the Pinyin pronunciation sort order, but other sort orders are commonly offered to end-users. Windows also provides the Surname sorting option for people’s names.

Taiwan has one system based on the pronunciation in the Bopomofo order and this is the prevalent system for collating Chinese in Taiwan. Whereas in Hong Kong SAR, users commonly sort by using stroke order.

Some Thai vowels and related vowels in certain scripts such as Lao are not represented in phonetic order when written. The exact list of such characters is given in the Unicode Character Database [UAX44]. For collation, they need to be rearranged.

Korean can be sorted based on the Hangeul pronunciation of the Hangeul and Hanja code points.
