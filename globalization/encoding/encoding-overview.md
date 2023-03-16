---
title: Encoding overview
description: The complex programming methods required for working with mixed-byte encodings, the involved process of creating new code pages every time another language requires computer support, and the importance of mixing and sharing information in a variety of languages across different systems were some of the factors motivating the creators of the Unicode encoding standard.
---

# Encoding overview

The complex programming methods required for working with mixed-byte encodings, the involved process of creating new code pages every time another language requires computer support, and the importance of mixing and sharing information in a variety of languages across different systems were some of the factors motivating the creators of the Unicode encoding standard.
Unicode originated through collaboration between Xerox and Apple.
An *ad hoc* committee of several companies then formed, and others, including IBM and Microsoft, rapidly joined.
In 1991, this group founded the Unicode Consortium whose membership now includes several leading Information Technology (IT) companies.
For more information on Unicode, visit the Unicode Consortium's site at [http://www.unicode.org](http://www.unicode.org).

Unicode is an especially good fit for the age of the Internet, since the worldwide nature of the Internet demands solutions that work in any language.
The World Wide Web Consortium (W3C) has recognized this fact and now expects all new RFCs to use Unicode for text.
Many other products and standards now require or allow use of Unicode; for example, XML, HTML, Microsoft JScript, Java, Perl, Rust, and C#.
Today, Unicode is the *de facto* character encoding standard accepted by all major computer companies.
While ISO 10646 is the corresponding worldwide *de jure* standard approved by all ISO members, the two standards include identical character repertoires and binary representations.

Unicode encompasses virtually all characters used widely in computers today.
It is capable of addressing more than 1.1 million code points.
The standard has provisions for 8-bit, 16-bit and 32-bit encoding forms.
The 16-bit encoding is used as its default encoding and allows for its million plus code points to be distributed across 17 "planes" with each plane addressing over 65,000 characters each.
The characters in Plane 0 - or as it is commonly called the "Basic Multilingual Plane" (BMP) — are used to represent most of the world's written scripts, characters used in publishing, mathematical and technical symbols, geometric shapes, basic dingbats, punctuation marks, and a few emoji.
But in addition to the support for characters in modern languages and for the symbols and shapes just mentioned, Unicode also offers coverage for other characters, such as less commonly used Chinese, Japanese, and Korean (CJK) ideographs, Arabic presentation forms, musical symbols, and most emojis.
Many of these additional characters are mapped beyond the original plane using an extension mechanism called "surrogate pairs."
Over 128,000 code points have already been assigned characters; the rest have been set aside for future use.
Unicode also provides Private Use Areas of over 137,000 locations available to applications for user-defined characters, which typically are rare ideographs representing names of people or places, historical scripts, or constructed languages.

Unicode rules, however, are strict about code-point assignment-each code point has a distinct representation.
There are also many cases in which Unicode deliberately does not provide code points.
Variants of existing characters are not given separate code points, because to do so would represent duplicate encoding of what is underlying the same character.
Examples are font variants (such as bold and italic) and glyph variants, which basically are different ways of representing the same characters.

For the most part, Unicode defines characters uniquely but some characters can be combined to form others, such as accented characters.
The most common accented characters which are used in French, German, and many other European languages exist in their pre-composed forms and are assigned code points.
These same characters can be expressed by combining a base character with one or more non-spacing diacritic marks.
For example, "a" followed by a non-spacing accent mark is displayed as "à."
Non-spacing accent marks make it possible to have a large set of accented characters without assigning distinct code points to every permutation of base character and accent.
This is useful for representing accented characters in written languages that are less widely used.
It's also useful for creating a variety of mathematical symbols.
The pre-composed characters are encoded in the Unicode Standard primarily for round-trip compatibility with other encodings.
The Unicode Standard contains strict rules for determining the equivalence of pre-composed characters to combining character sequences.
The Win32 API function FoldStringW maps multiple combining characters into pre-composed forms.

For all their advantages, Unicode Standards are far from a panacea for internationalization.
The code-point positions of Unicode elements do not imply a sort order and the organization is often unrelated to language usage.
To be useful, the mapping of Unicode points to fonts that can display them must either be handled by the application or the platform.
The [Common Locale Data Repository (CLDR)](http://cldr.unicode.org/) provides regional format and sorting information but requires that either the platform or a service manage that information.

Basing your software on the Unicode Standard is only one step in the internationalization process.
You still need to write code that adapts to cultural preferences or language rules.
For more information on other globalization considerations, see [Localizability overview](../localizability/overview.md "Localizability Overview"),
[Locale and Culture Awareness](../locale/locale-and-culture.md), and
[Input, display, and output](../input/text-input.md "Input, Display, and Output").

As a further caveat, not all Unicode-based text processing is a matter of simple character-by-character parsing.
Complex text-based operations such as hyphenation, line breaking, and glyph formation need to take into account the context in which they are being used (the relation to surrounding characters, for instance).
The complexity of these operations hinges on language rules and has nothing to do with Unicode as an encoding standard.
Instead, the software implementation should define a higher-level protocol for handling these operations.

In contrast, there are unusual characters that have very specific semantic rules attached to them; these characters are detailed in The Unicode Standard.
Some characters always allow a line break (for example, most spaces), whereas others never do (for instance, non-spacing or non-breaking characters).
Still other characters, including many used in Arabic and Hebrew, are defined as having a strong or weak directionality.
The Unicode Standard defines an algorithm for determining the display order of bidirectional text, and it also defines several "directional formatting codes" as overrides for cases not handled by the implicit bidirectional ordering rules to help create comprehensible bidirectional text.
These formatting codes allow characters to be stored in logical order but displayed appropriately depending on their directionality.
Neutral characters such as punctuation marks assume the directionality of the strong or weak characters nearby.
Formatting codes can be used to delineate embedded text or to specify the directionality of characters.
For more information on displaying bidirectional Unicode-based text, see Unicode's [BiDi Algorithm](http://unicode.org/reports/tr9/).

![Example Glyphs](./images/Example_Glyphs.png "Example Glyphs")

**Figure 1:** Precomposed and composite glyphs
