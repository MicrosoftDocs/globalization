---
title: Surrogate pairs and variation selectors
description: With the Unicode 16-bit encoding system, over 65,000 characters can be encoded 
---

# Surrogate pairs and variation selectors

## Surrogate pairs

With the Unicode 16-bit encoding system, over 65,000 characters can be encoded (2<sup>16</sup> = 65,536).
However, the total number of characters that needs to be encoded has actually exceeded that limit (to accommodate the emojis and symbols, CJK extension of characters, and historic scripts).
To find additional place for new characters, developers of the Unicode Standard decided to introduce the notion of surrogate pairs.
With surrogate pairs, a Unicode code point from range U+D800 to U+DBFF (called "high surrogate") gets combined with another Unicode code point from range U+DC00 to U+DFFF (called "low surrogate") to generate a whole new character, allowing the encoding of over one million additional characters.
Unlike multi-byte character set (MBCS) characters, high and low surrogates cannot be interpreted when they do not appear as part of a surrogate pair.
This avoids one of the major challenges with lead-byte/trail-byte processing of MBCS text.

These characters, encoded at code positions of U+10000 or higher, are synchronized with the international standard ISO/IEC 10646-2.
In addition to two Private Use Areas—plane 15 (U+F0000-U+FFFFD) and plane 16 (U+100000-U+10FFFD)—three supplementary planes are defined:

- Supplementary Multilingual Plane (SMP)-with code positions from U+10000 through U+1FFFF

- Supplementary Ideographic Plane (SIP)-with code positions from U+20000 through U+2FFFF

- Supplementary Special-purpose Plane (SSP)-with code positions from (SSP) U+E0000 through U+EFFFF

The SMP, or Plane 1, contains several historic scripts and several sets of symbols: emoji and related symbols, historic scripts, musical symbols, and mathematical symbols. The SIP, or Plane 2, contains a very large collection of additional unified Han ideographs, also known as CJK Extensions B, C, D, and E, as well as additional CJK Compatibility ideographs. The SSP, or Plane 14, contains a set of tag characters and a variation selector supplement.

## Variation Selection

Although the Unicode standard represents a large number of characters, the forms the glyphs take can vary from font to font and from culture to culture. A simple example is the difference between the following two characters.
<iframe src="char0067.html" height="60"></iframe>
For these types of difference there is no need to encode a different code point. This difference is mainly stylistic and is easily recognizable as the same character. However, during the process of encoding some characters there may be cases where characters with the same semantic meaning have different representation for contextual, historical, or stylistic reasons. In those cases, Unicode provides the variation selector method to represent these characters.

There are two sets of variants defined by Unicode:

- Standardized variation sequences

- Ideographic variation sequences as defined in the [Ideographic Variation Database (IVD)](http://www.unicode.org/ivd/)

Similar to surrogate pairs, the code point sequence is comprised of a base character followed by the variation selector (U+FE00-U+FE0F and U+E0100-U+E01EF, abbreviated VS1-VS16 and VS17-VS256).

For example, the character U+845B (“edible bean; surname”) may have a variation selector applied:
- U+845B: as used in the name of the Nishi-Kasai railway station: <span lang="ja">&#x897F;&#x845B;&#x897F;&#x99C5;</span>
  <iframe src="char845B.html" height="60"></iframe>
- U+845B with U+E0100 (VS17): as used in the name of Katsuragi City in Nara prefecture: <span lang="ja">&#x845B;&#xE0100;&#x57CE;&#x5E02;</span>
  <iframe src="char845BVS17.html" height="60"></iframe>

You will need a font that has this character defined for it to display correctly.

## End-User Defined Characters

[End-User Defined Characters](https://msdn.microsoft.com/library/dd317802(v=vs.85).aspx) (EUDCs) and
[Private Use Area](https://msdn.microsoft.com/library/dd317802(v=vs.85).aspx) (PUA) characters are used to represent custom characters that are shared across an entire corporation, organization, or government.
They are often used to display names or words with custom characters unavailable in other fonts.
These characters cannot be reliably shared across computers or systems.
