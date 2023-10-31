---
title: Text layout
description: Text layout is the process of converting a string of text characters into groups of glyphs .
ms.date: 10/31/2023
author: jowilco
---

# Text layout

Text layout is the process of converting a string of text characters into groups of glyphs displayed on a screen or printed page using specified font information and page layout. For [complex writing systems](../reference/universal-shaping-engine.md) (scripts), there are many factors that are involved in the correct display (rendering) of the string, including text shaping and text direction.

## Text shaping

Most platforms and browsers support correct text shaping automatically or by calling APIs (such as [DirectWrite](/windows/win32/directwrite)), but testers and developers should be aware that scripts’ glyph shapes may change depending on the context and should ensure correct behavior in applications.

### Ligatures

The simplest example of such shaping is a ligature. A ligature is a combination of two or more graphemes that form a single glyph. Many scripts combine multiple characters into a single shape. The rules of ligature used in ligature processing can be very complex in some scripts such as Arabic, while much simpler in others such as the Latin script. These rules not only depend on the individual characters of a given script, but also on the selected font used to draw them. Depending on the script, certain fonts are known to define hundreds of ligatures, while some other fonts do not use ligatures at all. Ligatures may have other effects such as cursor movement, text selection, and the positioning of diacritics relative to characters in scripts that support diacritics. Here are some examples of ligatures:

- The combination of f with the following letter is used frequently in typesetting for printed publications: ﬀ, ﬁ, ﬂ, ﬃ, ﬄ.
- A compound vowel, such as æ as a combination of the separate vowels “a” and “e”.
- The Arabic Lam and Alef: ل + ا = لا

| Individual Characters | Without Ligatures | With Ligatures |
| --------------------- | ----------------- | --------------- |
| ل م ح |  لمح | لمحـ |

### Contextual shaping

In some scripts the glyph displayed depends on the surrounding characters. A single Arabic character, for example, can take different shapes if it’s the first, middle, or last character in a word. Contextual shaping is the formation of correct sequences of characters, given these contexts.

In Greek, the glyph for the lowercase sigma character changes if it occurs at the end of the word, for example, **σ**οφό**ς** (wise).

### Character reordering

Character reordering is the rearrangement of characters in sequence from their logical order (the order in which they are input and stored) to their visual order (the order in which they are displayed).
Some scripts, such as Devanagari and Tamil, require reordering because vowel signs often appear to the left, below, or above a character that they follow in logical order. For example, consider the word हिन्दी (“Hindi” in Hindi, Devanagari script). The vowel इ is combined with the consonant ह and appears before it (in the form ि). However, the vowel ई is combined with the consonant द and appears after it (in the form ी).

### Combining characters

Combining characters are characters that modify and are displayed with other characters. Combining characters include diacritics and tone marks. The Unicode standard specifies many combining characters, mostly with a category of “Mark, nonspacing”. For glyphs used in many European languages, combinations of main and combining characters can be replaced with pre-composed characters. Here are some examples:

- ที่อยู่ (“address” in Thai) is comprised of:
  - ท - THAI CHARACTER THO THAHAN (U+0E17)
  - ◌ี - THAI CHARACTER SARA II (U+0E35)
  - ◌่ - THAI CHARACTER MAI EK (U+0E48)
  - อ - THAI CHARACTER O ANG (U+0E2D)
  - ย - THAI CHARACTER YO YAK (U+0E22)
  - ◌ู - THAI CHARACTER SARA UU (U+0E39)
  - ◌่ - THAI CHARACTER MAI EK (U+0E48)
- Tiếng Việt (“Vietnamese” in Vietnamese) contains ệ which could be comprised of any of:
  - LATIN SMALL LETTER E WITH CIRCUMFLEX AND DOT BELOW (U+1EC7)
  - LATIN SMALL LETTER E WITH CIRCUMFLEX (U+00EA) + COMBINING DOT BELOW (U+0323)
  - LATIN SMALL LETTER E WITH DOT BELOW (U+1EB9) + COMBINING CIRCUMFLEX ACCENT (U+0302)
  - LATIN SMALL LETTER E (U+0065) + COMBINING CIRCUMFLEX ACCENT (U+0302) + COMBINING DOT BELOW (U+0323)

For comparing and collating text that might be using combining characters or pre-composed characters, see [String normalization](../text/text-normalization.md).
