---
title: String normalization
description: TODO
ms.date: 1/23/2024
author: jowilco
---

# String normalization

<!--- TODO!!!
Links in the following topic need to point to this topic:
https://learn.microsoft.com/en-us/globalization/fonts-layout/text-layout

Add links in these topics:
https://learn.microsoft.com/en-us/globalization/design/security-guidelines
https://learn.microsoft.com/en-us/globalization/locale/sorting-and-string-comparison

Note this is a live-site issue, not an issue in the startup-staging branch.

TODO!!--->

Some Unicode characters have multiple equivalent binary representations consisting of sets of combining and/or composite Unicode characters. For example, the Latin small letter a with dieresis (umlaut) might be represented by either the character ä (U+00E4 LATIN SMALL LETTER A WITH DIAERESIS) or a (U+0061 LATIN SMALL LETTER A) with the combining dieresis character ¨ (U+0308 COMBINING DIAERESIS).

The [Unicode Standard](../encoding/unicode-standard.md) defines a process called normalization that returns one binary representation when given any of the equivalent binary representations of a character. By normalizing text data, you can compare the data for equivalence, irrespective of the choice of composed or decomposed forms of characters used in the data.

The Unicode Standard supports two types of equivalence between characters:

- *Canonical equivalence*: two code point sequences are assumed to have the same appearance and meaning.
- *Compatibility equivalence*: two code point sequences might have distinct appearances but could have the same meaning depending on the context.

For example:

- The character ž (U+017E LATIN SMALL LETTER Z WITH CARON) is **canonically equivalent** to z (U+007A LATIN SMALL LETTER Z) followed by a combining caron ◌̌ (U+030C COMBINING CARON)
- The character ǆ (U+01C6 LATIN SMALL LETTER DZ WITH CARON) is **compatibility equivalent** to d (U+0064 LATIN SMALL LETTER D) followed by ž (U+017E LATIN SMALL LETTER Z WITH CARON)

Note that appearance does not always indicate canonical equivalence. For example:

- Å: U+00C5 (LATIN CAPITAL LETTER A WITH RING ABOVE) and U+212B (ANGSTROM SIGN) are canonically equivalent.
- μ: U+03BC (GREEK SMALL LETTER MU) and U+00B5 (MICRO SIGN) might appear identical but have different meanings and are not canonically or compatibility equivalent.

The Unicode Standard defines four Normalization Forms:

| Normalization Form | Process |
|--------------------|---------|
| C (NFC)            | Canonical decomposition followed by canonical composition |
| D (NFD)            | Canonical decomposition |
| KC (NFKC)          | Compatibility decomposition followed by canonical composition |
| KD (NFKD)          | Compatibility decomposition |

When comparing strings that might contain composite characters or sequences of combining characters, you should normalize both strings. Libraries like ICU, frameworks like .NET, and programming languages like Java all support normalization methods.

It is critically important that you understand the effects of normalization when implementing system security. Visual or mixed script spoofing, for example, using the Cyrillic letter К (U+041A CYRILLIC CAPITAL LETTER KA) instead of the visually similar Latin letter K (U+004B LATIN CAPITAL LETTER K) is a common form of phishing. For more information about Unicode and security considerations, see [https://www.unicode.org/reports/tr36/](https://www.unicode.org/reports/tr36/).
