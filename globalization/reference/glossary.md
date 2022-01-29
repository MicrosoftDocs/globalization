---
title: Globalization glossary
description: A glossary of terms used in globalization and localization
---

# Globalization glossary

This article is a reference for common terminology and concepts in globalization

## adaptation

The process of producing translation by adapting existing material in a closely related language and locale.
For example, en-US (United States) content can be produced by adapting en-GB (Great Britain) content.
Similarly, fr-FR content (France) is often adapted for fr-CA (Canada).
Adaptation can be much less expensive than producing a new translation.
Much of the adaptation process can be a simple replacement of words or phrases for a different spelling or terminology.

## ANSI

Acronym for American National Standards Institute.
The term "ANSI" referring to a Windows code page is a historical reference, but the usage is commonly found.
An "ANSI application" is a non-Unicode code-page-based application.

## ASCII

Acronym for American Standard Code for Information Interchange.
A 7-bit encoding of text.
The 128 characters of ASCII are the common denominator in most code pages, UTF-8, and Unicode.
In all encodings that contain ASCII, the each ASCII character has the same numeric value.
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
A given character set may have a number of encodings.

## codepage

An encoding of a character set, labelled by a number and a name.
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
See also: codepage, MBCS, SBCS

## encoding

When used in the context of globalization, an encoding is a scheme whereby text is represented as a sequence of bytes.

## internationalization

The process of making an application usable in multiple locales, according to the locale preference of the user.

## globalization

The process of enabling an application so that it can be used all around the world.

## glyph

A distinct graphical unit of text.
Commonly referred to as a character, but a glyph may be a composite of multiple characters.
For example, the characters A and E may be displayed using the composite glyph Æ.

## localization

The process of adapting a product so that it is suitable for use in a specific locale, including translating the applications user interface and user assistance.).

## machine translation (MT)

Automated translation, commonly by way of statistical methods, neural-networks, or other artificial intelligence techniques.
Machine translation (MT) may be used as a substitute for human translation if the result meets your quality goals.
More frequently, MT is used to assist human translators by providing suggested translations of a text.

## Multi-Byte Character Set (MBCS)

A set of characters encoded using a sequence of one or more bytes per character.
See also: codepage DBCS, SBCS

## pseudo-translation

An automated transformation of source text that simulates some effects of translation that commonly cause issues with a product.
For example, pseudo-translation may lengthen text to uncover truncations and buffer overruns.
It can also add accents and characters from foreign scripts to uncover rendering and font issues.
The transformation remains understandable enough that testers can still use the product without knowing a foreign language.
Resources that have not been exposed to localization are readily apparent in a pseudo-translated application.

## Single-Byte Character Set (SBCS)

A character set that is encoded as a stream of single bytes.

See also: codepage, DBCS, MBCS

## transcreation

The process of creating new content unique to a locale, borrowing the general look, feel, and voice of existing source content.
Transcreation is used when a literal translation of the source material is inadequate.
Marketing material is often prepared by transcreation rather than translation.

## translation

The process of producing text, graphics, or other material in a target language from material in a source language.

## translation memory (TM)

A database or repository containing the translations of source text to one or more target languages.
A translation memory can be leveraged to reduce the costs of translation by recycling an existing translation of a source string, either an exact match of the source or a "fuzzy" (similar) match.

## transliteration

The process of transforming content in one script to another script.
For example, Serbian may be semi-automatically transliterated between Cyrillic and Latin.
Depending on the language and the scripts, this may be done completely automated or with the assistance of automation, which can reduce the cost of translation.

## UTF-8

An encoding of Unicode using a sequence of bytes.

## XLIFF

An industry standard XML-based file format for localization.
You may hear it pronounced "x-leaf".
