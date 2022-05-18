---
title: Internationalization Checklist
description: A summary of areas that should be validated to ensure localizability.
---

# Internationalization checklist

Here is a summary of areas that should be validated to ensure localizability.

## Operating system support

* If appropriate, all application languages should run on all supported operating system languages using data in any language.
 The user's data may not be in the same language or script as the application's user interface, and may be multilingual.

## Reading and saving data to files

* Ensure that the desired range of characters can be read/written. Best if all text data is Unicode.

* Data written in the application running one language should be able to be read when the application is running any other supported language.

* If the written file is intended for use with a third-party application, ensure that the third-party application can read the file correctly once data in different languages and scripts is included.

## Localizability

* All strings are externalized to translatable resource file.

* Concatenation is never used to assemble messages or user interface labels.

* Individual strings are not used in different contexts.

* Context is provided to translators through developer comments in resource files.

* Non-localizable strings are clearly annotated (locked), or separated from localizable resources.

* Text and messages are devoid of jargon, slang, and cultural references.

* Consistent and correct terminology is used in strings.

## Locale and Cultural Awareness

The conventions and formats of various kinds of data vary by locale.
A global application must be able to handle user's data by the conventions and standards of the user's locale.

* [Calendars, date, and time](../locale/calendar-differences.md)

<!--NYI * [Case mapping](../text/case-mapping.md)] -->

* [Currency formatting](../locale/currency-formatting.md)

* [Measurement units](../locale/units-of-measurement.md)

* [Number formatting](../locale/number-formatting.md)

* [Paper and envelope size](../locale/paper-size.md)

<!--NYI * [Payment methods](../internationalization/payment-methods.md) -->

* [Postal address formats](../locale/addresses.md)

<!-- NYI * [Punctuation, separators](../internationalization/punctuation-separators.md) -->

* [Sorting, comparison, and search](../locale/sorting-and-string-comparison.md)

<!-- NYI * [Spell-checker or thesaurus/dictionary support](../locale/dictionaries-spelling.md) -->

* [Telephone number formatting](../locale/telephone-number.md)

<!-- NYI * [Text parsing and validation](../text/parsing-input.md) -->

## Display

* Responsive design: use adaptive layout, have graceful truncation and wrapping.

* The application honors system defaults.

* The appropriate fonts are used for the language of the user interface and user's data.

* Applications should support any keyboard and Input Method editor (IME).
