---
title: Pseudolocalization
description: How do you verify that your product is localizable without actually localizing into a real language? By faking it with pseudo-localization.
---

# Pseudolocalization

Pseudolocalization is a strategy where you can verify that your product is localizable without actually localizing into a real language.
Pseudolocalization is informally referred to as simply "pseudo" when you're working in the context of localization.

## Pseudo translation

Pseudo translation is an automated transformation of source text.
It simulates common effects of translation that commonly cause issues with a product.
The transformation remains understandable enough that the product can still be used and tested without knowing a foreign language.

Resources that haven't been exposed to localization are readily apparent because they won't be pseudo-translated.

- Add accents and characters from other scripts.

  For example, the letter `a` is transformed into any one of `äáàāāǎǎăăåå`, selected at random.
  A parallel transformation is applied to other letters.

- Expand the string to simulate the longer strings that result from translation.

  When the source language is English, a good heuristic is to lengthen the text by 40%.
  In practice, there can be extreme cases where a string may be 200% or even 400% longer when translated into a real language.
  Strings that are one or two words commonly grow proportionally longer than longer strings.

- Pad text to the expansion length using characters from other scripts, such as Greek, Cyrillic, Asian, and Indic scripts.

  Adding text from other scripts can reveal clipping and font-handling issues.

- Add delimiters to the start and end of each string.
  For example, wrap the string in a pair of `^` .

  Wrapping a string instantly reveals truncations in the product user interface because the delimiter will be missing.
  Concatenations will also be revealed by the occurrence of `^^` in displayed text.

## Pseudo locales

You can discover issues with formatting and parsing numbers, dates, times, and currency by using a pseudo locale.
A pseudo locale will contain date, time, and other formatting options that challenge common assumptions about formats.

Windows defines three pseudo-locales that you can use to test your application.
[Pseudo Locales](/windows/win32/intl/pseudo-locales) lists the ones available in Windows:

| Pseudo-locale | Locale name |
| --- | --- |
| Base                | qps-ploc  |
| Mirrored            | qps-plocm |
| East Asian-language | qps-ploca |

### Locale identifiers for pseudo

Care must be taken to use locales that follow the rules for locale identifiers.

When Microsoft was pioneering pseudo localization in Windows, they used tk-TM (Turkmen - Turkmenistan):
a valid locale name and one that Windows wasn't shipping at the time.
This choice didn't work out well when the next release of Windows included tk-TM as a real locale.
The collision caused many bugs, especially in the build and testing systems that assumed tk-TM was the pseudo-locale.
Lesson learned: use locale names that are well-formed but will never describe a real language or locale.

You may find references using ps-PS as a pseudo locale, but ps-PS can be interpreted as Pashto (Palestinian Authority).
It's a well-formed locale name, but not one that makes very much sense.
Pashto isn't commonly spoken in that region.

<!--
This story is told in "One of my colleagues is the "Pseudo Man" (a rich source of puns in conversation!)"
on Michael Kaplan's MSDN blog, which was unfortunately lost when MSDN blogs were decommissioned.

The text of Michael's blogs are available (without images) at
http://archives.miloush.net/michkap/archive/2011/04/11/10152035.html
 -->

If you look at RFC4646 (Tags for Identifying Languages) section 2.2.1.3:

> The subtags in the range 'qaa' through 'qtz' are reserved for private use in language tags.
> These subtags correspond to codes reserved by ISO 639-2 for private use.
> These codes MAY be used for non-registered primary language subtags (instead of using private use subtags following 'x-').

The Windows pseudo locales all start with `qps`, so they are in the allowed reserved range.

