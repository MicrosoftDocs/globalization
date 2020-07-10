---
title: Internationalization Checklist
description: A summary of areas that should be validated to ensure localizability.
ms.date: 05/22/2020
---

# Internationalization checklist

## Operating system support

- If appropriate, all application languages should run on all supported operating system languages using data in any language.

## Reading and saving data to files

- Ensure that the desired range of characters can be read/written.
- Data written in the application running one language should be able to be read when the application is running any other supported language.
- If the written file is intended for use with a third-party application, ensure that the third-party application can read the file correctly once data in different languages is included.

## Localizability

- All strings are externalized to translatable resource file.
- Concatenation is never used to assemble sentence fragments.
- Strings are never reused in multiple contexts.
- If supported in the resource file format, context is provided to translators.
- Locked/non-localizable strings are clearly annotated.
- Text and messages are devoid of slang and cultural references.
- Consistent and correct terminology is used in strings

## Locale/Cultural Awareness

- [Collation, comparison, and search](../locale/sorting-and-string-comparison.md)
- Text conversion (e.g. upper/lower case, text-to-speech, digits to words)
- [Number formatting](../locale/number-formatting.md)
- [Currency formatting](../locale/currency-formatting.md)
- [Date formatting](../locale/date-formatting.md)
- [Calendar differences](../locale/calendar-differences.md)
- [Time formatting](../locale/time-formatting.md)
- Time zones, daylight saving time
- Address formats
- [Telephone numbers/Telephone number formats](../locale/telephone-number.md)
- [Measurement Units](../locale/units-of-measurement.md)
- [Paper and envelope size](../locale/paper-size.md)
- Payment methods
- Punctuation, separators
- Spell-checker or thesaurus/dictionary support
- Parsing, validation (e.g. full-width vs. half-width digits)

## Display

- Responsive design (avoid hardcoding, graceful truncation/wrapping, etc.)
- Honor system defaults
- Font support
- Keyboard and IME support
