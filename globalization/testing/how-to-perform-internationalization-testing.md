---
title: How to perform internationalization testing
description: This article is a checklist of common issues with internationalization and localization that can be identified during testing.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# How to perform internationalization testing

This article describes the four stages of internationalization testing mentioned in [When to perform internationalization testing](when-to-perform-internationalization-testing.md) and offers a detailed [checklist](#internationalization-checklist) of important issues as well as some specific test cases you can use.

## Review your code

Code reviews for internationalization can take place long before translation work. When reviewing your code, be sure it meets the following requirements:

1. Ensure that your UI can be translated efficiently and correctly. For a list of things to check, see [Internationalization in What to look for when testing internationalized products](how-to-perform-internationalization-testing.md#internationalization).
1. Ensure that your UI displays appropriately on screens with different resolutions and aspect ratios and that users can interact with the UI, for example, to input text with an [IME](../input/input-method-editors.md).

These can be done at the same time as reviewing your code for general internationalization, including:

1. Ensure that your text data isn't limited to a particular [script](../fonts-layout/writing-systems.md) or language (it might even be multilingual). The data should also work regardless of [locale](../locale/locale.md), [time zone](../locale/time-zones.md), or [units of measurement](../locale/measurement-units.md).
1. Ensure that you can display your text and UI in different scripts. You can input text in non-Latin scripts using [Input Method Editors (IME)](../input/input-method-editors.md).
1. Ensure that your app respects the conventions and settings of the OS. These include [locale](../locale/locale.md), [sort order](../locale/sorting-and-string-comparison.md), capitalization, folder names, and registry keys.
1. Ensure that your app respects the conventions of the target market. These include the formatting of names, [postal addresses](../locale/addresses.md), [phone numbers](../locale/telephone-numbers.md), and using the right [paper sizes](../locale/paper-size.md) and [units of measurement](../locale/measurement-units.md).
1. Ensure that your product is appropriate for the target market. This includes following local laws and regulations, using the preferred payment methods, and avoiding culturally sensitive issues. For more information, see [How to release products internationally](../methodology/how-to-release-products-internationally.md).

## Review the source language UI and documentation

You should ensure the terminology used in your app’s user interface and support documentation is clear, consistent, and unambiguous. Translators find it harder to do a good job if the UI and the documentation refer to the same thing with several different words, or if technical slang is used. The source text should also avoid nontechnical slang and culture-specific references. These checks improve internationalization, which leads to better translations with less expense, and also helps to give your international users the same level of user experience everywhere.

## Test with a pseudolocalized version of your app

Pseudolocalization (informally, "pseudo") can be the most effective way of finding internationalization bugs that would only be detected when translating your app. Pseudolocalization gives you a "translation" without the cost of producing one. You can create pseudolocalized resources using the [Multilingual App Toolkit](/windows/apps/design/globalizing/use-mat) or other translation tools. You can test a pseudolocalized version of your app anytime you would typically test its source language version. For general information on pseudolocalization, see [Pseudolocalization](../methodology/pseudolocalization.md).

Some internationalization issues such as truncations, concatenation or strings that are not exposed to localization are easier to spot on a pseudolocalized version than on a real language. And unlike a real translated version, a pseudolocalized version is easy to use even if you don't understand other real languages.

Once you have pseudolocalized your product, [test it as you would a real language](how-to-perform-localization-testing.md), covering both functional and visual aspects, paying special attention to [internationalization issues](how-to-perform-internationalization-testing.md).

### Pseudomirroring

If you're planning to create a localized version of a product that supports a right-to-left writing system like Arabic or Hebrew, you should consider pseudomirroring testing, which you can implement as part of pseudolocalization. For an application targeted for these markets, you should follow the development and design rules outlined in [User interface layout](../fonts-layout/interface-layout.md) to allow for UI mirroring.

Pseudomirroring then verifies that these rules were followed. You can use pseudolocalization to generate resource files that contain right-to-left scripts. By using these resource files in conjunction with enabling mirroring in your application, you can test the mirroring behavior anytime you would typically test the source language version.

## Start localization with a small set of languages

Let’s assume that the product you want to release internationally is going to need localization into many different languages. For many people the instinctive solution is to release all those languages at the same time, or at least as many as possible. However, it might be more cost-effective to start with just one or two languages and add more in subsequent releases.

As discussed previously, [pseudolocalization](#test-with-a-pseudolocalized-version-of-your-app) can be extremely helpful, but it can never catch all issues. If you complete a validation through pseudolocalization (and address issues that have been found), then start the actual localization and localization testing with a small subset of pilot languages, you may identify additional issues before they impact your broader localization efforts. These typically include issues that specifically impact the translation process, ranging from tooling to challenges with the source text.

If you decide to start small, choose one or two languages for which you can easily organize localization and [localization testing](how-to-perform-localization-testing.md). For instance, you might have experience with the language from previous projects, or your organization employs people who speak the language.

It's helpful to choose languages for which the localization is especially likely to expose localization problems. For example, with German, the translated text is likely to be longer and uses a different sentence structure. Arabic and Hebrew text is written from right-to-left and the UI for these languages should similarly be mirrored. Languages like Chinese and Japanese use a very large range of characters.

Every language is different, and localizing just one or two can't reveal every possible issue. Adding pseudolocalization and pilot localization may seem like extra steps that could slow down the pace of planned localized releases. When combined strategically, each step can significantly reduce the effort required in the next step, especially with a large number of target languages. This can not only reduce costs, it can also speed up the release of each planned language at the right quality by dramatically shortening its validation and bug fixing cycle.

## Internationalization checklist

Here's a summary of areas that should be validated during the four stages described to ensure internationalization is done properly.

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

### Internationalization

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
