---
title: Software Internationalization
description: Design and develop your application using internationalization (i18n) best practices to ensure global support.
ms.date: 3/26/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:03/26/2024
---

# Software Internationalization

Internationalization (abbreviated as _i18n_ – 18 letters between "I" and "n") is the process of designing and developing your application such that it can support users in different global markets. When working on any software application, it's important to think about internationalization from the very beginning of its design. Your first iteration or release might not be translated into another language; however, it's likely your application will be used by customers all over the world.

Coding for world-readiness affects implementation across the entire product. The decisions that you make early in the project can determine your ability to deliver to other markets later. The user interface design is the most affected, but world-readiness must be considered in many other areas.

The following sections discuss key themes for world-readiness. All sections are applicable even for a single-language user interface (UI) or application; however, the final three sections cover ensuring that your application is ready for [localization](../localization/localize-software.md) (abbreviated as _l10n_ – 10 letters between "l" and "n"). Localization is the process of adapting or translating your app's localizable resources to meet the language, cultural, and political requirements of the local markets that the app is intended to support. One component of localization is translating UI text. Even if you aren't planning to create localized versions of your product, it's time-consuming and expensive to update your code to support multiple languages if your plans change in the future. It's therefore best practice to follow the principles in the following sections, even if your product only supports a single language.

## Data encoding

You should ensure that any user data isn't limited to a particular [script](../fonts-layout/writing-systems.md). If your application can use [Unicode](../encoding/unicode-standard.md), it can be helpful in ensuring that users are able to use a large variety of scripts and writing systems. If your application is limited to a fixed set of [code pages](../encoding/code-pages.md), you might need to ensure that data can be [converted](../text/encoding_text_conversion.md) between the various encodings. If your application sends or receives information from other applications or components, you should also ensure that differences in encodings can be handled, or at a minimum fail gracefully.

Any data that is stored shouldn't be limited to a specific country/region, time zone, or unit of measurement. For example, while users might want to enter data using the local time, it might be preferable to store the data as Coordinated Universal Time (UTC).

## Text display

You should ensure that your application can display user data and UI text in different [scripts](../fonts-layout/writing-systems.md). You might not have plans to translate your application into East Asian languages, such as Chinese, or languages that use [bi-directional](../fonts-layout/text-directionality.md) writing systems, such as Arabic. However, you might have users of these languages, so user data and user input shouldn't be limited by script or [font](../fonts-layout/fonts.md).

## Locale awareness

You should ensure that your application respects conventions and settings from the operating system, especially [locale](../locale/locale.md)-related [settings](../locale/system-user-settings.md). These locale-related settings include [numeric](../locale/number-formatting.md), [currency](../locale/currency-formats.md), [time, and date](../locale/date-time-formats.md) formats. The choice of locale also affects language-related features such as [sort order](../locale/sorting-and-string-comparison.md) and [capitalization](../text/case-mapping.md).

You should also ensure that your application responds correctly to changes to features related to the language of the operating system, such as default folder names and registry keys.

## Market conventions

You should ensure that your application respects the conventions of each target market. These conventions might be broad, but could include [name format](../locale/addresses.md#personal-names-and-name-order), [postal address format](../locale/addresses.md#postal-address), [telephone number format](../locale/telephone-numbers.md), [paper sizes](../locale/paper-size.md), and [units of measurement](../locale/measurement-units.md). The use of bold and italic text might vary by script and market.

## Translatability

You should ensure that the UI can be translated correctly. Translations tend to be more accurate when the source material is well-written. Consistent use of terminology and clear source text can help users of a single-language product, especially when those users might not be native speakers of that language.

Strings should be [externalized](../internationalization/externalize-resources.md) and you should avoid [concatenation](../internationalization/concatenation.md). Where supported by the resource file format, consider adding contextual metadata  to each string especially when [placeholders/variables](../internationalization/message-formatting.md) are used. You should avoid using text in images because images tend to be expensive to recreate during the translation process.

It's best practice to externalize all strings; however, for strings that aren't intended for end users such as debugging or logging messages, consider using separate resource files. You can then choose whether to translate resource files that only contain debugging or logging messages.

## UI and translations

Where possible, [responsive designs](../fonts-layout/adaptive-ui.md) support releasing localized versions of products faster, as you don't need to spend time resizing the UI due to string-length expansion or contraction. You can plan for future localization into various languages using [pseudolocalization](../methodology/pseudolocalization.md). Pseudolocalization allows you to validate how well your application responds to changes in string length and characters from different scripts or writing systems. Pseudolocalization also allows you to validate whether your application can support [mirroring](../fonts-layout/mirroring.md) for languages that use bidirectional writing systems.

[Icons, images, and colors](../fonts-layout/images-icons-colors.md) might need to be adapted for target markets. You should ensure that icons, images, and colors can easily be customized.

Users should be able to interact with the product using appropriate [keyboards](../input/keyboards.md) or [input method editors](../input/input-method-editors.md) (IME). You shouldn't assume that specific key combinations are available to users in other languages.

## Target market support

You should ensure that your application is appropriate for users in your target markets. The scope of this work can be broad, and can include:

- specific features to support the market
- country/regional standards and legal requirements
- preferred or alternative platforms
- external data sources
- payment methods
- compatibility with other products
- hosting environments in target markets to avoid latency issues
