---
title: What to look for when testing internationalized products
description: This article is a checklist of common issues with internationalization and localization that can be identified during testing.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# What to look for when testing internationalized products

This article offers a checklist of issues important to your internationalization testing and some specific test cases you can use.

## Internationalization checklist

Here's a summary of areas that should be validated to ensure internationalization is done properly.

### Operating system (OS) support

- Verify that all app languages work with all supported OS languages using data in any language. This can be done in two phases:
  - Before localization, test the app on different language versions of the OS. This can uncover many issues early.
  - After localization, test that the translated app versions work and look correctly on different language versions of the OS.
- Verify the application’s ability to work with localized OS objects such as special folders, account names, and registry entries.

### Reading and saving data to files

- Data written using one app language should be able to be read in all other app languages and with all supported OS languages.
- Validate that the full range of characters can be read, written, and displayed. Confirm that the desired text encoding is used in files. Unicode is usually the best option for text data. Other types of encoding may be used, typically for legacy support, but require additional care.
- Files that contain field delimiters, such as CSV files, require additional care, as delimiters can vary regionally. Verify interoperability with systems using different regional settings.
- Files that contain regionally formatted data, such as dates, times, and numbers, also require additional care. Using a "neutral" format for these might be preferable. But if that isn't an option, verify interoperability with systems using different regional settings.
- If the written file is intended for use with a third party app, validate its compatibility. Any third party app restrictions should be handled gracefully. Data written for or read by the third party app should be preserved. This might require limiting the data that can be written. Also, ensure that the third party app can read the file correctly once data in different languages and scripts is included.

### Locale and cultural awareness

#### Data formatting

- [Number formatting](../locale/number-formatting.md)
- [Currency formatting](../locale/currency-formats.md)
- [Date and time formatting](../locale/date-time-formats.md)
- [Calendars](../locale/calendars.md)

#### Text support

- [Collation, sorting, comparison, and search](../locale/sorting-and-string-comparison.md) returns appropriate results: see the [Sort order](#sort-order) test data
- Text conversions such as [case mapping](../text/case-mapping.md), text-to-speech, and digits to words are handled appropriately: see the [Letter case](#letter-case) test data
- [Text parsing and validation](../text/parsing-input.md) (for example, full-width vs. half-width digits)
- Validate that user data can be entered and displayed using various languages and scripts.
- Verify that font selection and font fallback are used correctly to avoid *tofu* (for example, the small box (􏿾) character that appears when a glyph isn't available in the current font).
- Text from writing systems that use different orientation or directionality than the application’s language should be handled gracefully.

#### Local conventions and standards

- Time zones and daylight saving time
- Calendar differences

### Localizability

- Text and messages are devoid of jargon, slang, and cultural references, making it appropriate for non-English native speakers.
- Consistent and correct terminology is used in strings.
- All strings are externalized to translatable resource files.
- Context is provided to translators through developer comments in resource files (if supported by the resource file format).
- Individual strings aren't reused in different contexts.
- Nonlocalizable strings are clearly identified or separated from localizable resources.
- Concatenation is never used to assemble messages or user interface labels.
- Images avoid using embedded text.

### Cultural awareness and market conventions

- [Postal address formatting](../locale/addresses.md)
- [Telephone number formatting](../locale/telephone-numbers.md)
- [Paper and envelope sizes](../locale/paper-size.md)
- [Units of measurement](../locale/measurement-units.md)
- [Punctuation and separators](../internationalization/punctuation-separators.md)
- [Personal names and name order](../locale/addresses.md#personal-names-and-name-order)

### Display

- Follow responsive design principles: use adaptive layout, have graceful truncation and wrapping.
- Ensure the app honors system defaults and settings.
- Ensure that the appropriate fonts are used for the language of the UI and user's data.

### Input

- Ensure the app supports any keyboard and [Input Method editor (IME)](../input/input-method-editors.md) for entering text.

### Target market support

- [Payment methods](../internationalization/payment-methods.md) (support, availability)
- [Internal spell-checker, text prediction, or thesaurus/dictionary support](../locale/dictionaries-spelling.md) for the language

### Localization

- Translations are correct: terminology, style, and meaning are accurately conveyed
- All functionality works in the localized versions
- All strings display in the correct language
- UI layout is correct
- Language-specific functional customization (if any)
- Compliance with local requirements, including appropriately translated documentation and license agreement

## Test data for internationalization testing

You should set up a set of test data to facilitate testing. The type of data depends on the use case: a database, saving files, given and family names, for example. Include a broad range of characters, and use characters with specific goals (Unicode, sort, casing, and so on).

### Letter case

If the application converts the case of text, you can verify the functionality with scripts that don't have uppercase and lowercase symbols, such as Cyrillic, East Asian scripts, and Hebrew.

You can also use text where there are locale-specific rules for case conversion, such as Turkish.

Turkish uses upper and lower case, dotted and dotless letter "I".

Unlike other languages written in the Latin script, Turkish "I"s don't gain or lose their dots when changing case.

| Code point | Unicode Character Name                | Letter                    | Opposite case (Turkish) |
|------------|---------------------------------------|---------------------------|-------------------------|
| U+0049     | :::no-loc text="LATIN CAPITAL LETTER I":::                | **`I`**                   | **<code>&#x0131;</code>**   |
| U+0069     | :::no-loc text="LATIN SMALL LETTER I":::                  | **`i`**                   | **<code>&#x0130;</code>**   |
| U+0130     | :::no-loc text="LATIN CAPITAL LETTER I WITH DOT ABOVE"::: | **<code>&#x0130;</code>** | **`i`**                     |
| U+0131     | :::no-loc text="LATIN SMALL LETTER DOTLESS I":::          | **<code>&#x0131;</code>** | **`I`**                     |  

### Sort order

If the application displays text in a sorted order, you should verify that the sort order is correct for the supported locales and target markets. Here are several cases that you could consider for testing.

#### Chinese

China has two different sort orders, one by pronunciation and one by stroke order. The results vary based on the sort order the user chooses.

| Pronunciation Order | Unicode Value | PinYin | Stroke Order | Unicode Value | PinYin |
|--- | --- | --- | --- | --- | --- |
| :::no-loc text="䠀"::: | U+4800  | :::no-loc text="chang"::: | :::no-loc text="𠀀"::: | U+20000 | :::no-loc text="he"::: |
| :::no-loc text="㠀"::: | U+3800  | :::no-loc text="dao":::   | :::no-loc text="㐀"::: | U+3400  | :::no-loc text="qiu"::: |
| :::no-loc text="䀀"::: | U+4000  | :::no-loc text="fan":::   | :::no-loc text="䄀"::: | U+4100  | :::no-loc text="huo"::: |
| :::no-loc text="䘀"::: | U+4600  | :::no-loc text="fu":::    | :::no-loc text="䀀"::: | U+4000  | :::no-loc text="fan"::: |
| :::no-loc text="𠀀"::: | U+20000 | :::no-loc text="he":::    | :::no-loc text="䐀"::: | U+4400  | :::no-loc text="ji"::: |
| :::no-loc text="䄀 ":::| U+4100  | :::no-loc text="huo":::   | :::no-loc text="㠀"::: | U+3800  | :::no-loc text="dao"::: |
| :::no-loc text="䐀 ":::| U+4400  | :::no-loc text="ji":::    | :::no-loc text="㔀"::: | U+3500  | :::no-loc text="qing"::: |
| :::no-loc text="𣀀"::: | U+23000 | :::no-loc text="lei":::   | :::no-loc text="䠀"::: | U+4800  | :::no-loc text="chang"::: |
| :::no-loc text="㔀"::: | U+3500  | :::no-loc text="qing":::  | :::no-loc text="㘀"::: | U+3600  | :::no-loc text="zuo"::: |
| :::no-loc text="㐀"::: | U+3400  | :::no-loc text="qiu":::   | :::no-loc text="𣀀"::: | U+23000 | :::no-loc text="lei"::: |
| :::no-loc text="㘀"::: | U+3600  | :::no-loc text="zuo":::   | :::no-loc text="䘀"::: | U+4600  | :::no-loc text="fu"::: |

#### Turkish

Under Turkish conventions, dotless "I" (the uppercase "I" (U+0049) or the lowercase "ı" (U+0131)) precedes dotted "I" (the uppercase "İ" (U+0130) or lowercase "i" (U+0069)). This order isn't the same as the order of the values of the letter's Unicode code points.

#### Other examples from European languages

- Characters with diacritical marks might be sorted with their base letter (for example, French) or they might be sorted as separate letters (for example, Estonian). Å (U+00C5 LATIN CAPITAL LETTER A WITH RING ABOVE) is sorted after Z in several Nordic languages. In German, sort order can depend on context. For example, in phone books, ä (U+00E4 LATIN SMALL LETTER A WITH DIAERESIS) in a person’s name is treated as ae, while sorted after a (U+0061 LATIN SMALL LETTER A) in most other cases.
- Czech: The digraph “CH” is treated as a separate letter appearing between H and I.
- French: words are sorted in the order where the accents appear within each word. For example, côte is sorted before coté.
- Lithuanian: The Lithuanian alphabet has 32 letters, and Y (U+0059 LATIN CAPITAL LETTER Y) is sorted before J (U+004A LATIN CAPITAL LETTER J) unlike English where Y is sorted before Z (U+005A LATIN CAPITAL LETTER Z)
