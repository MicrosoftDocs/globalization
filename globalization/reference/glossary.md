---
title: Globalization glossary
description: A glossary of terms used in globalization, localization, and internationalization.
---

# Globalization glossary

This article is a reference for common terminology and concepts in globalization, localization, and internationalization.

## adaptation

The process of producing translation by adapting existing material in a closely related language and locale.
For example, en-US (United States) content can be produced by adapting en-GB (Great Britain) content.
Similarly, fr-FR content (France) is often adapted for fr-CA (Canada).
Adaptation can be much less expensive than producing a new translation.
Much of the adaptation process can be a direct replacement of words or phrases for a different spelling or terminology.

## ANSI

Acronym for American National Standards Institute.
The term "ANSI" referring to a Windows code page is a historical reference, but the usage is commonly found.
An "ANSI application" is a non-Unicode code-page-based application.

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
See also: code point

## character set

A defined set of characters, sometimes referred to as a repertoire.
Although the name of a character set is sometimes used as a synonym for the encoding of that character set, the concepts are distinct.
A given character set may have several encodings.

## codepage

An encoding of a character set, labeled by a number and a name.
Used most often in association with the ID number assigned to the encoding in a given system.
For example, Windows codepage 1252, ANSI Latin 1

See also: DBCS, encoding, MBCS, SBCS

## code point

A unique number assigned to a particular character in a character set.
See also: character code

## Content Management System (CMS)

A software system for managing a body of content.

## Double-Byte Character Set (DBCS)

A set of characters encoded using a sequence of one or two bytes per character.
See also: [codepage](#codepage), [MBCS](mbcs), [SBCS](#sbcs)

## encoding

When used in the context of globalization, an encoding is a scheme whereby text is represented as a sequence of bytes.

## internationalization

The entire process of bringing software to worldwide markets, including [globalization](#globalization), [localizability](#localizability), [localization](#localization).
Internationalization sometimes includes special market customization (also known as "Marketization".

## globalization

The process of enabling an application so that it can be used all around the world.

The process of developing applications or writing content whose features and characteristics are language-, culture-, and market- neutral.
The application can operate correctly in all locales, and it can be localized (translated) without recompilation.
It honors user and system settings for language, culture, country/region, and related data formatting.
The code will support any combination of editing language, user locale, or user interface language with a single worldwide binary.

## glyph

A distinct graphical unit of text.

A glyph is commonly referred to as a "character", but this term isn't precise.
A glyph may be a composite of multiple characters or a combination of a base character with modifiers (diacritics).
For example, the characters A and E may be displayed using the composite glyph Æ, and the letter a with an acute accent is the glyph á.

## localization

The process of adapting a product so that it's suitable for use in a specific locale, including translating the applications user interface and user assistance.

## localizability

The state of an application in which resources are maintained in a localizable format, separate from the executable code.
The goal is to avoid any source code modification during the localization process.
You can achieve that only if you design and develop your application with localization in mind.

## machine translation (MT)

Automated translation, commonly by way of statistical methods, neural-networks, or other artificial intelligence techniques.
Machine translation (MT) may be used as a substitute for human translation if the result meets your quality goals.
More frequently, MT is used to assist human translators by providing suggested translations of a text.

## Multi-Byte Character Set (MBCS)

A set of characters encoded using a sequence of one or more bytes per character.
See [codepage](#codepage), [DBCS](dbcs), [SBCS](#sbcs).

## pseudolocalization

Localizing a product using artificial locales and automated mechanical transformation of source text.

Pseudolocalization allows you to implement and test the localizability of your product.
This process reveals many bugs that can appear when localizing into a real language, without incurring the cost and delay of human translation.

See [pseudotranslation](#pseudotranslation).

## pseudotranslation

An automated transformation of source text that simulates some effects of translation that commonly cause issues with a product.
For example, pseudo-translation may wrap and lengthen text to uncover truncations and buffer overruns.
It can also add accents and characters from other scripts to uncover rendering and font issues.

The transformation remains understandable enough that the product can still be used and tested without knowing a foreign language.
Resources that have not been exposed to localization are readily apparent.

## Single-Byte Character Set (SBCS)

A character set that is encoded as a stream of single bytes.

See also: [codepage](#codepage), [DBCS](dbcs), [MBCS](#mbcs)

## transcreation

The process of creating new content unique to a locale, borrowing the general look, feel, and voice of existing source content.
Transcreation is used when a literal translation of the source material is inadequate.
Marketing material is often prepared by transcreation rather than translation.

## translation

The process of producing text, graphics, or other material in a target language from material in a source language.

## translation memory (TM)

A database or repository containing the translations of source text to one or more target languages.

A translation memory can reduce the costs of translation by recycling an existing translation of a source string.
The translation may be exact match of the source, a "fuzzy" (similar) match, or the best fit based on a confidence threshold.

Translation memories are also used to assist translators and train machine translation models.

## transliteration

The process of transforming content in one script to another script.
For example, Serbian may be semi-automatically transliterated between Cyrillic and Latin.
Depending on the language and the scripts, transliteration may be completely automated or combined with post-editing by a human being.
Whether automated or semi-automated, the cost of translation is reduced by the technique.

## UTF-8

An encoding of Unicode using a sequence of bytes.

## XLIFF

An industry standard XML-based file format for localization.
You may hear it pronounced "x-leaf".
