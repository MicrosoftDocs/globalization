---
title: Globalization glossary
description: A glossary of terms used in globalization, localization, and internationalization.
ms.topic: article
ms.date: 01/01/2022
---

# Globalization glossary

This article is a reference for common terminology and concepts in globalization, localization, and internationalization.

## adaptation

The process of producing translation by adapting existing material in a closely related language and locale.
For example, en-US (United States) content can be produced by adapting en-GB (Great Britain) content.
Similarly, fr-FR content (France) is often adapted for fr-CA (Canada).
Adaptation can be much less expensive than producing new translations.
Much of the adaptation process is a direct replacement of words or phrases with different spellings or terminology.
In some cases, human review and post-editing are used along with automated adaptation.

## ANSI

Acronym for American National Standards Institute.
The term "ANSI" referring to a Windows code page is a historical reference, but the usage is commonly found.
An "ANSI application" is a non-Unicode codepage-based application.

## ASCII

Acronym for American Standard Code for Information Interchange.
A 7-bit encoding of text.
The 128 characters of ASCII are the common denominator in most code pages, UTF-8, and Unicode.
In all encodings that contain ASCII as a subset, each ASCII character has the same numeric value.
 "A" is always code point 65 (`0x41`).

## Byte Order Mark (BOM)

A sequence of bytes that can be interpreted to determine the byte order of code units in an encoding.
A BOM may also be used as a file signature to indicate the format of a file.

## character code

A unique number or byte sequence assigned to a particular character in a character set.
See also: [code point](#code-point)

## character set

A defined set of characters, sometimes referred to as a repertoire.
Although the name of a character set is sometimes used as a synonym for an encoding of that character set, the concepts are distinct.
A given character set may have several encodings.

See also: [code point](#code-point)

## codepage

An encoding of a character set, labeled by a number and a name.
Used most often in association with the ID number assigned to the encoding in a given system.
For example, Windows codepage 1252, ANSI Latin 1.

See also: [DBCS](#dbcs), [encoding](#encoding), [MBCS](#mbcs), [SBCS](#sbcs)

## code point

A unique number assigned to a particular character in a [character set](#character-set).
See also: [character code](#character-code), [encoding](#encoding)

## <a name="cms"></a>Content Management System (CMS)

A software system for managing a body of content.

## <a name="dbcs"></a>Double-Byte Character Set (DBCS)

A set of characters encoded using a sequence of one or two bytes per character.
See also: [codepage](#codepage), [MBCS](#mbcs), [SBCS](#sbcs)

## encoding

When used in the context of globalization, an encoding is a scheme whereby text is represented as a sequence of bytes.

## internationalization

The entire process of bringing software to worldwide markets, including [globalization](#globalization), [localizability](#localizability), and [localization](#localization).
Internationalization may also include special market customization (also known as "Marketization".

You may see internationalization referred to by the shorthand **I18n**. The "18" refers to the number of omitted letters between "I" and "n".

## globalization

The process of enabling an application so that it can be used all around the world.

The process of developing applications or writing content whose features and characteristics are language-, culture-, and market- neutral.
The application can operate correctly in all locales, and it can be localized (translated) without recompilation.
It honors user and system settings for language, culture, country/region, and related data formatting.
The code will support any combination of editing language, user locale, or user interface language with a single worldwide binary.

You may see globalization referred to by the shorthand **G11n**. The "11" refers to the number of omitted letters between "G" and "n"..

## glyph

A distinct graphical unit of text.

A glyph is commonly referred to as a "character", but this term isn't precise.
A glyph may be a composite of multiple characters or a combination of a base character with modifiers (diacritics).
For example, the characters A and E may be displayed using the composite glyph Æ, and the letter a with an acute accent is the glyph á.

## locale

A body of properties identified by locale name (sometimes called "locale code").

A locale name is formed from the language code, an optional script code, and the code for a country or region.

A locale contains the locale-specific information required to format dates, times, numbers, and currency.
The locale also contains information such as:

* system of measurement
* calendar
* currency symbol ($, €, ¥, £, ฿, ₱, ₭, ...)
* currency code (USD, AUD, GBP, EUR, INR, DKK, YEN, ...)

The Common Locale Data Repository (CLDR) is a standardized source of locale data.
CLDR is used by libraries such as the International Components for Unicode (ICU), globalize.js, Windows NLS APIs, and .NET APIs.

## localization

The process of adapting a product so that it's suitable for use in a specific locale, including translating the applications user interface and user assistance.

You may see localization referred to by the shorthand **L10n**. The "10" refers to the number of omitted letters between "L" and "n".

## localizability

The state of an application in which resources are maintained in a localizable format, separate from the executable code.
The goal is to avoid any source code modification during the localization process.
You can achieve that only if you design and develop your application with localization in mind.

## <a name="mt"></a>machine translation (MT)

Automated translation, commonly by way of statistical methods, neural-networks, or other artificial intelligence techniques.
Machine translation (MT) may be used as a substitute for human translation if the result meets your quality goals.
More frequently, MT is used to assist human translators by providing suggested translations of a text.

## <a name="mbcs"></a>Multi-Byte Character Set (MBCS)

A set of characters encoded using a sequence of one or more bytes per character.
See [codepage](#codepage), [DBCS](#dbcs), [SBCS](#sbcs).

## <a name="posix"></a>Portable Operating System Interface (POSIX)

An IEEE 1003.1 standard to ensure compatibility when programs are moved from one Unix-like platform to another. It is intended for both application and system developers. The most recent specification is [IEEE Std 1003.1-2017](https://standards.ieee.org/ieee/1003.1/7101/).

## pseudolocalization

Localizing a product using artificial locales and automated mechanical transformation of source text.

Pseudolocalization allows you to implement and test the localizability of your product.
This process reveals many bugs that can appear when localizing into a real language, without incurring the cost and delay of human translation.

You may see pseudolocalization and related areas gathered under the umbrella term **pseudo**.

See [pseudotranslation](#pseudotranslation).

## pseudotranslation

An automated transformation of source text that simulates some effects of translation that commonly cause issues with a product.
For example, pseudo-translation may wrap and lengthen text to uncover truncations and buffer overruns.
It can also add accents and characters from other scripts to uncover rendering and font issues.

The transformation remains understandable enough that the product can still be used and tested without knowing a foreign language.
Resources that haven't been exposed to localization are readily apparent.

You may see pseudotranslation and related areas gathered under the umbrella term **pseudo**.

## <a name="sbcs"></a>Single-Byte Character Set (SBCS)

A character set that is encoded as a stream of single bytes.

See also: [codepage](#codepage), [DBCS](#dbcs), [MBCS](#mbcs)

## script

In the context of text handling and Unicode, a script is the writing system used to write a particular language.
Some languages are commonly written in multiple scripts.
For example, Japanese documents often contain text in the Han, Katakana, Hiragana, and Latin scripts.

A script code may be included in a locale name when it's important to distinguish the writing system.
For example, to distinguish Serbian Cyrillic (`sr-cyrl`) from Serbian Latin (`sr-latn`).
The script code is omitted from the locale name when there's an unambiguous primary script for a language.
For example, the the code: `latn` (for the Latin script) is normally omitted in the locale names for English, French, German, Italian, and Spanish.

See also:

* [locale](#locale)
* [Unicode Script Property - Unicode.org](http://www.unicode.org/reports/tr24)
* [ISO 15924 Alphabetical Code List - Unicode.org](https://www.unicode.org/iso15924/iso15924-codes.html)

## segmentation

In localization, segmentation is the process of breaking up a source text into translation units.
Each translation unit that can be translated independently.
The ideal segment is a sentence, but the process works well in practice without perfect identification of sentence boundaries.

Segmentation is always used when localizing content (documentation or other prose).
For software string resources, each string is treated a translatable unit.
Some localization vendors or systems may provide segmentation for software strings as an option.

A [translation memory](#tm) stores translations for each translation unit so that translations can be recycled.

## transcreation

The process of creating new content unique to a locale, borrowing the general look, feel, and voice of existing source content.
Transcreation is used when a literal translation of the source material is inadequate.
Marketing and legal material is often prepared by transcreation rather than translation.

## translation

The process of producing text, graphics, or other material in a target language from material in a source language.

## <a name="tm"></a>Translation Memory (TM)

A database or repository containing the translations of source text to one or more target languages.

A translation memory can reduce the costs of translation by recycling existing translations of source text.
The translation provided may be based on an exact match of the source text, a "fuzzy" (similarity) match, or a best fit based on an algorithm.

Each entry in a TM may also contain context information to help provide better matching for a given source text.
Context information may include:

* source file name
* resource identifier
* adjacent text
* digest or hash of adjacent text

The result of querying a TM for the translation of a segment may be a list of candidates, ranked by a confidence level.
The confidence is often expressed as a percentage match.

Translation memories are also used to train machine translation models.

## translation unit

A unit of text that can be translated independently.
In software localization, each string resource is a translation unit.
In content localization, the source text undergoes [segmentation](#segmentation) to generate a set of translation units.

## transliteration

The process of transforming content in one script to another script.
For example, Serbian may be semi-automatically transliterated between Cyrillic and Latin.
Depending on the language and the scripts, transliteration may be automated or combined with post-editing by a human being.
Whether automated or semi-automated, the cost of translation is reduced by the technique.

## UTF-8

An encoding of Unicode using a sequence of bytes.

## <a name=xliff></a> XML Localization Interchange File Format (XLIFF)

XLIFF is an industry standard XML-based file format for localization.
You may hear it pronounced "x-leaf".

The XLIFF standard is a product of the [:::no-loc text="OASIS XML Localisation Interchange File Format (XLIFF) TC":::](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=xliff) ("TC" stands for "Technical Committee").

The following versions of the standard are in current use in the localization industry:

* [XLIFF 1.2](https://www.oasis-open.org/standard/xliffv1-2/)
* [XLIFF 2.1](https://www.oasis-open.org/standard/xliffv2-1/)
