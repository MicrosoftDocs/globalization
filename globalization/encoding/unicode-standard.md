---
title: The Unicode standard
description: TODO
ms.date: 1/23/2024
author: jowilco
---

# The Unicode standard

The [Unicode Standard](https://www.unicode.org/standard/standard.html) is a character encoding that endeavors to support all historical and writing system using a single character encoding. Unicode is the de facto character encoding standard accepted by all major computer companies. Many products and standards now require or allow use of Unicode, for example, XML, HTML, Microsoft JScript, Java, Perl, Rust, and C#. While ISO 10646 is the corresponding worldwide de jure standard approved by all ISO members, the two standards include identical character repertoires and binary representations.

Compared to older mechanisms for handling character and string data, Unicode simplifies software localization and improves multilingual text processing. By using Unicode to represent character and string data in your applications, you can enable universal data exchange capabilities as well as supporting multiple languages in a single application. The Unicode Standard and associated specifications provides the following:

- Allows any combination of characters, drawn from any combination of scripts and languages, to co-exist in a single document.
- Defines multiple encodings of its single character set: UTF-8, UTF-16, and UTF-32. Conversion of data among these encodings is lossless.
- Defines semantics for each character.
- Standardizes script behavior and text rendering.
- Provides a standard algorithm for bidirectional text.
- Defines cross-mappings to other standards.

## Character and script support

Unicode encompasses virtually all characters used widely in computers today. For example, Version 15.0 of the Unicode Standard contains [149,186 characters](https://www.unicode.org/versions/stats/charcountv15_0.html) and supports [161 scripts](https://www.unicode.org/standard/supported.html). In addition to the characters that support scripts, Unicode includes many other types of characters, such as:

- characters used in publishing
- mathematical and technical symbols
- geometric shapes
- basic dingbats
- punctuation marks
- emoji
- Arabic presentation forms
- musical symbols

### Unicode encoding and planes

The original version of Unicode was designed as a 16-bit encoding, which limited the support to 65,536 (2^16) code points. Version 2.0 of the Unicode Standard increased the range from U+0000..U+10FFFF. These ranges are grouped in planes - 65,536 (2^16) code points per plane. Planes are subdivided into [Unicode blocks](https://www.unicode.org/Public/UCD/latest/ucd/Blocks.txt). Each Unicode block is a contiguous range of code points that share a common purpose, such as supporting a single script.

| Plane | Range        | Name                                             | Description |
|-------|--------------|--------------------------------------------------|-------------|
| 0     | 0000-FFFF    | Basic Multilingual Plane (BMP)                   | <ul><li>Support for most modern languages including the most common CJK Unified Ideographs</li><li>Symbols, such as currency</li><li>Private Use Area</li></ul> |
| 1     | 10000–1FFFF  | Supplementary Multilingual Plane (SMP)           | <ul><li>Non-CJK ideographic historic scripts</li><li>Modern scripts</li><li>Symbols, such as musical notation</li><li>Emoji</li></ul> |
| 2     | 20000-2FFFF  | Supplementary Ideographic Plane (SIP)            | Additional CJK Unified Ideographs, mostly historical, uncommon, or variants |
| 3     | 30000-3FFFF  | Tertiary Ideographic Plane (TIP)                 | CJK Unified Ideographs, mostly historical, that are not encoded in the BMP or SIP |
| 4-13  | 40000-DFFFF  | unassigned                                       | |
| 14    | E0000-EFFFF  | Supplementary Special-purpose Plane (SSP)        | Tags  and variation sequence selectors |
| 15-16 | F0000-10FFFF | Supplementary Private Use Area planes (SPUA-A/B) | Private Use Area |

The Unicode Standard specifies that the complete range of Unicode code points can be converted to unique code unit sequences using one of seven *Unicode encoding schemes* or *Unicode Transformation Formats* (UTF). The table below compares the Unicode encoding schemes.

| Unicode encoding scheme | Unit size | Byte order    | Number of bytes (bits) per character | Notes |
|-------------------------|-----------|---------------|--------------------------------------|-------|
| UTF-8                   | 8 bits    | n/a           | 1-4 bytes (8-32 bits)                | BOM can be used to indicate encoding. |
| UTF-16                  | 16 bits   | BOM required  | 2-4 bytes (16-32 bits)               | |
| UTF-16BE                | 16 bits   | Big-endian    | 2-4 bytes (16-32 bits)               | |
| UTF-16LE                | 16 bits   | Little-endian | 2-4 bytes (16-32 bits)               | Default encoding for Windows. |
| UTF-32                  | 32 bits   | BOM required  | 4 bytes (32 bits)                    | |
| UTF-32BE                | 32 bits   | Big-endian    | 4 bytes (32 bits)                    | |
| UTF-32LE                | 32 bits   | Little-endian | 4 bytes (32 bits)                    | |

#### Byte order and byte order marks

UTF-8 is interpreted as a sequence of bytes:

- The first 128 code points (U+0000..U+007F) are equivalent to the ASCII code points and only require one byte to encode.
- The range U+0080..U+07FF requires two bytes
- The range U+0800..U+FFFF (the remainder of the BMP) requires three bytes
- Code points in planes 1-16 require four bytes

The UTF-16 encoding form encodes code points in one or two 16-bit code units. The UTF-32 encoding form encodes code points in a single 32-bit code unit.

Both UTF-16 and UTF-32 can use little-endian (least-significant byte at the smallest memory address) or big-endian (most-significant byte at the smallest memory address) byte orders. While the byte orders for UTF-16LE, UTF-16BE, UTF-32LE, and UTF-32BE are unambiguous, UTF-16 and UTF-32 require a byte order mark (BOM, U+FEFF) at the beginning of the stream or file to indicate the byte order.

When the BOM is encountered at the beginning of the stream or file, the order of the bytes of the BOM will indicate the order of the remainder of the stream or file.

- FE FF (UTF-16) or 00 00 FE FF (UTF-32) will indicate big-endian
- FF FE (UTF-16) or FF FE 00 00 (UTF-32) will indicate little-endian

A BOM can also be used with UTF-8, but it is only used as a signature to distinguish, for example, a UTF-8 stream or file from an ASCII stream or file.

#### Unicode Transformation Formats and file sizes

As UTF-32 requires four bytes for every Unicode code point, it would seem that UTF-32 would always lead to larger file sizes than UTF-16 and UTF-8. However, file size also depends on the code points that the file contains.

- If the file only contains characters in the range U+0000..U+007F, UTF-8 will use 1 byte per character, UTF-16 will use 2 byte per character, while UTF-32 will use 4 byte per character. In other words, the UTF-32 file will be 4 times larger than the UTF-8 file.
- If the file only contains characters in the range U+0800..U+D7FF, UTF-8 will use 3 bytes per character, UTF-16 will use 2 byte per character, while UTF-32 will use 4 byte per character. In other words, the UTF-8 file will be 50% larger than the UTF-16 file.
- If the file only contains characters in the supplementary planes, UTF-8, UTF-16, and UTF-32 will all use 4 bytes per character and so all files will be the same size.

### Surrogate Pairs

UTF-16 uses either one or two 16-bit code units (2 or 4 bytes) to represent the Unicode code points. A single code unit can represent code points in the range U+0000..U+FFFF. For code points in the supplementary planes (range U+10000...U+10FFFF) a pair of code units, called a *surrogate pair*, are required. The first (high) surrogate is a 16-bit code value in the range U+D800 to U+DBFF. The second (low) surrogate is a 16-bit code value in the range U+DC00 to U+DFFF.

Unicode code points in the range U+D800..U+DFFF have been reserved for use by UTF-16. When reading a UTF-16 stream, it is unambiguous whether a byte is a lead byte (high surrogate) or a trail byte (low surrogate) of a multi-byte (surrogate pair) character, which is a common challenge with MBCS text.

## The Unicode Character Database and character properties

In addition to the encoding of characters, the Unicode Standard also published the [Unicode Character Database](https://unicode.org/ucd/)  which is a catalog of the character and a corresponding set of semantics that describe each character including character type, use, directionality, and combining behavior. By prescribing how each character should be displayed.

For example, the Unicode character set includes numerous combining characters, such as U+0308 ("¨"), a combining dieresis or umlaut. Unicode can often represent the same glyph in either a ''composed'' or a ''decomposed'' form: for example, the composed form of "Ä" is the single Unicode code point "Ä" (U+00C4), while its decomposed form is "A" + "¨" (U+0041 U+0308). Unicode does not define a composed form for every glyph. For example, the Vietnamese lowercase "o" with circumflex and tilde ("ỗ") is represented by U+006f U+0302 U+0303 (o + Circumflex + Tilde). The composed characters are encoded in the Unicode Standard primarily for round-trip compatibility with other encodings. The Unicode Standard contains strict rules for determining the [equivalence of composed characters to combining character sequences](../text/text-normalization.md).

## Unicode characters and text layout

Not all Unicode-based text processing is a matter of simple character-by-character parsing. Complex text-based operations such as [hyphenation](../locale/dictionaries-spelling.md), [line breaking](../fonts-layout/line-and-word-breaking.md), and [glyph formation](../fonts-layout/text-layout.md) need to consider the context in which they are being used (the relation to surrounding characters, for instance). The complexity of these operations hinges on language rules and has nothing to do with Unicode as an encoding standard. Instead, the software implementation should define a higher-level protocol for handling these operations.

In contrast, there are unusual characters that have very specific semantic rules attached to them; these characters are detailed in The Unicode Standard. Some characters always allow a line break (for example, most spaces), whereas others never do (for instance, non-spacing or non-breaking characters). Many characters used in Arabic and Hebrew are defined as having a strong or weak [directionality](../fonts-layout/text-directionality.md). The Unicode Standard defines an algorithm for determining the display order of bidirectional text, and it also defines several "directional formatting codes" as overrides for cases not handled by the implicit bidirectional ordering rules to help create comprehensible bidirectional text.

The code-point positions of Unicode elements do not imply a [sort order](../locale/sorting-and-string-comparison.md) and the organization is often unrelated to language usage. To implement sorting, the mapping of Unicode points to fonts that can display them must either be handled by the application or the platform. The [Common Locale Data Repository](../reference/cldr.md) (CLDR) provides the regional format and sorting information that can be used to implement sorting and collation.

### Variation Selection

Although the Unicode standard represents many characters, the forms the glyphs take can vary from font to font and from culture to culture. A simple example is the difference between the following two characters. The first using a serif font while the second is using a sans-serif font.

<iframe src="char0067.html" height="60"></iframe>

For these types of difference there is no need to encode a different code point. This difference is mainly stylistic and is easily recognizable as the same character. However, during the process of encoding some characters there may be cases where characters with the same semantic meaning have different representations for contextual, historical, or stylistic reasons. In those cases, Unicode provides the variation selector method to represent these characters.

There are three sets of variants defined by Unicode:

- [Standardized variation sequences](https://www.unicode.org/Public/UCD/latest/ucd/StandardizedVariants.txt)
- Ideographic variation sequences as defined in the [Ideographic Variation Database](http://www.unicode.org/ivd/) (IVD)
- [Emoji variation sequences](https://unicode.org/Public/emoji/latest/emoji-sequences.txt)

A variation sequence is defined as a base character followed by a variation selector (U+FE00-U+FE0F and U+E0100-U+E01EF, abbreviated VS1-VS16 and VS17-VS256).

The example below shows GREATER-THAN BUT NOT EQUAL TO (U+2269) with and without VS1 (U+FE00). Depending on the fonts available in your browser, the first character should display with a slanted line indicating “not equals” while the second character should display with a vertical line.

<iframe src="char2269_variation.html" height="80"></iframe>

For example, the character U+845B (“edible bean; surname”) can be used with a variation selector as defined in the in the Ideographic Variation Database (IVD):

- U+845B: as used in the name of the Nishi-Kasai railway station: 西葛西駅

  <iframe src="char845B.html" height="60"></iframe>

- U+845B with U+E0100 (VS17): as used in the name of Katsuragi City in Nara prefecture: 葛󠄀城市

  <iframe src="char845BVS17.html" height="60"></iframe>

> [!TIP]
> You will need a font that has this character defined for it to display correctly.

For more information about using variation sequences with emoji, see [Emoji](../fonts-layout/emoji.md).
