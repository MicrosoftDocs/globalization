---
title: Internationalization Checklist
description: A summary of areas that should be validated to ensure localizability.
ms.date: 05/22/2020
---

# Internationalization checklist

Here is a summary of areas that should be validated to ensure localizability.

## Operating system support

- If appropriate, all application languages should run on all supported operating system languages using data in any language.
  The language of a user's data may not be the same language as the application's user interface, and may be multilingual.

## Reading and saving data to files

- Ensure that the desired range of characters can be read/written.
- Data written in the application running one language should be able to be read when the application is running any other supported language.
- If the written file is intended for use with a third-party application, ensure that the third-party application can read the file correctly once data in different languages is included.

## Localizability

- All strings are externalized to translatable resource file.
- Concatenation is never used to assemble messages or user interface labels.
- Individual strings are not used in multiple contexts.
- Context is provided to translators.
- Non-localizable strings are clearly annotated (locked).
- Text and messages are devoid of slang and cultural references.
- Consistent and correct terminology is used in strings.

## Locale and Cultural Awareness

The conventions and formats of various kinds of data vary by locale.
A global application must be able to handle user's data by the conventions and standards of the user's locale.

- [Sorting, comparison, and search](../locale/sorting-and-string-comparison.md)
- [Case mapping](../text/case-mapping.md)]
- [Number formatting](../locale/number-formatting.md)
- [Currency formatting](../locale/currency-formatting.md)
- [Calendars, date, and time](../locale/calendar-date-time.md)
- [Postal address formats](../locale/addresses.md)
- [Telephone number formatting](../locale/telephone-numbers.md)
- [Measurement units](../locale/measurement-units.md)
- [Paper and envelope size](../locale/paper-size.md)
- [Payment methods](../internationalization/payment-methods.md)
- [Punctuation, separators](../internationalization/punctuation-separators.md)
- [Spell-checker or thesaurus/dictionary support](../locale/dictionaries-spelling.md)
- [Text parsing and validation](../text/parsing-input.md)

## Display

- Responsive design (avoid hard coding positions, graceful truncation/wrapping, etc.)
- Honor system defaults
- Font support
- Keyboard and IME support
