---
title: Pseudolocalization
description: How do you verify that your product is localizable without actually localizing into a real language? By faking it with pseudolocalization.
author: v-pdempsey
ms.date: 6/7/2022
---

# Pseudolocalization

With pseudolocalization, you can verify that your product is localizable without actually localizing into a real language.
Many potential issues in localization can be discovered independently from actual translation.
The pseudolocalization strategy can be applied in the earliest phases of development before translation begins.
The strategy is sustained throughout the development cycle for continual testing and validation.

The pseudolocalization techniques described here are informally referred to as simply "pseudo".
The shorthand term is commonly understood when you're working in the context of localization.

## Pseudotranslation

Pseudotranslation is an automated transformation of source text.
It simulates common effects of translation that commonly cause issues with a product.
The transformation is readable enough that the product can still be used and tested without knowing a foreign language.

While pseudotranslation can help discover many potential issues with localization, it isn't a complete replacement for validating the translated application.

Resources that haven't been exposed to localization are readily apparent because they won't be pseudo-translated.

A pseudotranslation process can:

- Add accents and characters from other scripts.

  For example, the letter `a` is replaced by any one of `αäáàāāǎǎăăåå` selected at random.
  The digits 1-9 can be replaced by circled digits &#x2460;-&#x2468; (U+2460 - U+2468).
  A similar replacement can be applied to other characters.

- Expand the string to simulate the longer strings that can result from translation.
  Expanded strings reveal layout and truncation issues.

  When the source language is English, a good heuristic is to lengthen the text by 40%.
  In practice, there can be extreme cases where a string may be 200% or even 400% longer when translated into a real language.
  Strings that are one or two words commonly grow proportionally longer than strings with more words.

  Translations can also be shorter than the source text.
  Shrinkage generally causes fewer issues than growth and is challenging to simulate, so isn't used with pseudo.

- Pad text to the expansion length using characters from other scripts, such as Greek, Cyrillic, Asian, and Indic scripts.

  Adding text from other scripts helps reveal clipping and font-handling issues.

- Add delimiters to the start and end of each string.
  For example, wrap the string in a pair of caret characters (`^`).

  Wrapping a string instantly reveals truncations in the product user interface because the delimiter is missing.
  Concatenations will also be revealed by paired delimiters embedded in the displayed text.

- Add a unique identifier so that you can easily locate the resource in the source.
  The identifier can be a hash of the resource identifier or some other data to uniquely identify the resource.

## Pseudotranslation tools

Pseudotranslation is supported by the [Multilingual App Toolkit Editor](https://developer.microsoft.com/windows/downloads/multilingual-app-toolkit/).
Commercial and open source localization tools may also provide an option for pseudotranslation.

## Pseudo locales

You can discover issues with formatting and parsing numbers, dates, times, and currency by using a pseudo locale.
A pseudo locale will contain date, time, and other formatting options that challenge common assumptions about formats.

Windows defines three pseudo locales that you can use to test your application.
[Pseudo Locales](/windows/win32/intl/pseudo-locales) lists the ones available in Windows:

| Pseudo-locale | Locale name |
| --- | --- |
| Base                | qps-ploc  |
| Mirrored            | qps-plocm |
| East Asian-language | qps-ploca |

You can test with pseudo locales even if you aren't using pseudotranslation, or haven't enabled it yet.  
<!-- Does CLDR include pseudo locales? -->

### Locale identifiers for pseudo

Care must be taken to use locale names that follow the rules for locale identifiers.

When Microsoft was pioneering pseudolocalization for Windows, they used tk-TM (Turkmen - Turkmenistan):
a valid locale name and one that Windows wasn't shipping at the time.
This choice didn't work out well when the next release of Windows included tk-TM as a real locale.
The collision caused many bugs, especially in the build and testing systems that assumed tk-TM was the pseudo-locale.
Lesson learned: use locale names that are well-formed but will never describe a real language or locale.

<!--
This story is told in "One of my colleagues is the "Pseudo Man" (a rich source of puns in conversation!)"
on Michael Kaplan's MSDN blog, which was unfortunately lost when MSDN blogs were decommissioned.

The text of Michael's blogs are available (without images) at
http://archives.miloush.net/michkap/archive/2011/04/11/10152035.html
 -->

You may find references using ps-PS as a pseudo locale, but ps-PS can be interpreted as Pashto (Palestinian Authority).
While ps-PS is a well-formed locale name, it's not one that makes very much sense.
Pashto isn't commonly spoken in that region.

RFC4646 (Tags for Identifying Languages) section 2.2.1.3 says:

> The subtags in the range 'qaa' through 'qtz' are reserved for private use in language tags.
> These subtags correspond to codes reserved by ISO 639-2 for private use.
> These codes MAY be used for non-registered primary language subtags (instead of using private use subtags following 'x-').

The Windows pseudo locales all start with `qps`, so they are in the allowed reserved range.

International Components for Unicode (ICU) provides for two pseudo locale names: en-XA (A for Accents) and en-XB (B for bidirectional).
