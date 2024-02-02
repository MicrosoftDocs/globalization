---
title: Case mapping
description: Understand the importance of case mapping in applications and the challenges it presents in different languages and locales.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Case mapping

When creating applications, you might want to convert, or map, text to uppercase, to lowercase, or to title case (initial letter of every word in a string of text is capitalized). There are several reasons for wanting to use case mapping, including:

- Case-insensitive text comparison
- For display reasons, such as adding emphasis or formatting titles

One method of converting between uppercase and lowercase characters is to use the relative positions in the appropriate codepage. For example, in Unicode, LATIN CAPITAL LETTER A (U+0041) is separated from LATIN SMALL LETTER A (U+0061) by 32 code points. Similarly, LATIN CAPITAL LETTER B (U+0042) is separated from LATIN SMALL LETTER B (U+0062) by 32 code points. However, this strategy only works in a small number of situations:

- Many scripts only have a single case (unicameral scripts). These include Arabic, Hangul, and Thai. Latin, Greek, and Cyrillic are examples of bicameral scripts, and these scripts include lowercase and uppercase characters.
- There isn't always a 1:1 correspondence of lowercase and uppercase characters. For example:
  - In English, LATIN SMALL LETTER I (U+0069) is equivalent to LATIN CAPITAL LETTER I (U+0049). However, Turkish uses LATIN CAPITAL LETTER I WITH DOT ABOVE (U+0130) as the uppercase equivalent to U+0069 and LATIN SMALL LETTER DOTLESS I (U+0131) as the lowercase equivalent to U+0049.
  - GREEK CAPITAL LETTER SIGMA (U+03A3) has two lowercase equivalents, GREEK SMALL LETTER SIGMA (U+03C3) and GREEK SMALL LETTER FINAL SIGMA (U+03C2), where U+03C2 is only used at the end of words.
- Case mapping might not be appropriate for a specific language. For example, in German, nouns start with an uppercase letter. Converting to lowercase might change the meaning of the word.

## Case mapping and locale

Libraries like ICU, frameworks like .NET, and programming languages like Java typically have locale-aware versions of methods for case mapping. You should always consider which locale should be used when using case mapping methods. In most cases, the default is to use the current locale; however, there might be situations where you want to use the locale most appropriate to the application language or the text to be converted. You might even want to use an invariant locale so that you'll get consistent behavior across different configurations.

Even locale-aware versions of case mapping can't address all the challenges with converting cases. For example,

- In English, style guides have differences in which small words should have initial capitals for title case.
- In French, while the Académie Française [specifies](https://www.academie-francaise.fr/questions-de-langue#5_strong-em-accentuation-des-majuscules-em-strong) that accents should be used on uppercase characters, conventional use might avoid accents on uppercase characters.
- Case mapping might not be appropriate for abbreviations or technical text. For example, the SI unit for time is s (second), while the SI unit for electrical conductance is S (siemens).
- Case mapping for proper nouns and trademarked names might not be appropriate.
- Case mapping isn't always reversible. In the previous examples involving Greek and Turkish, there might not be a 1:1 equivalent of uppercase and lowercase characters, or the mapping might be language dependent.

## Case and Unicode

Each character in the [Unicode Character Database](https://unicode.org/ucd/) can have mappings defined for lowercase, uppercase and title case. Additional rules are defined for characters like ligatures and differences from default behavior like the Turkish i/İ and ı/I pairs.

The [ICU](https://icu.unicode.org/) library takes advantage of this data to provide a set of case mapping, case detection, and case folding (mapping strings to a canonical form for string comparison) methods. Case folding typically results in lowercase characters; however, characters in the Cherokee script resolve to uppercase characters. Case folding isn't context-, language-, or locale-sensitive; however, you can specify whether to use mappings for languages like Turkish.
