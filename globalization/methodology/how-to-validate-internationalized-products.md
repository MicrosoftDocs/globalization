---
title: How to validate international products
description: An overview of issues involved in testing your product for international release.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# How to validate international products

Planning an international product release is an involved process. You need to consider legal requirements, banking and payments, product delivery, regional support, and the localization process. All of which you can only do after deciding on your overall international strategy. These concerns are discussed in [How to release products internationally](how-to-release-products-internationally.md).

As you develop your application, you'll need to ensure that your application functions correctly for users in all target markets for all languages supported by your product. This article gives a quick overview of the kind of issues that need to be considered. For a more detailed technical overview, see [Validating products for international release](../testing/how-to-test-internationalized-products.md).

As you [internationalize](software-internationalization.md) your product, you should start validating support for worldwide users with localizability testing. You'll need to validate that:

- Data, especially text data, isn't limited to any [script or writing system](../fonts-layout/writing-systems.md), and that data can be exchanged between different systems.
- Your application can display user data and UI text in the scripts used in the target markets
- Your application respects the conventions and settings from the operating system, especially [locale](../locale/locale.md)-related settings, such as numeric formats, sort order, and capitalization.
- Your application respects the conventions of each target market, such as postal address format and paper sizes.
- Your application is ready to translate. This work includes [externalizing strings](../internationalization/externalize-resources.md), but also ensuring that the source material uses terminology consistently and avoids culture-specific references and slang. You should aim to ensure that your source language text becomes accessible for users who aren't native speakers.
- Your application should support different screen sizes, resolutions, and orientations. You should ensure that different [keyboard layouts](../windows-keyboard-layouts.md) and [Input Method Editors](../input/input-method-editors.md) are compatible with your application.

Once you have validated that your product is internationalized, the next step is [localization](../localization/localization-overview.md), followed by [localization testing](../testing/how-to-test.md). The testing should cover all of your application languages. You should also ensure that your application is able to run on any version of the OS language and is able to handle data in any language.

Localization testing should ensure all the user interface text is displayed correctly following the conventions of each target language and culture. It should convey the same meaning as the source text. You should also ensure that your localized product meets the needs of the target market. The scope of this work can be very broad, and can include:

- Specific features to support the market
- Country/regional standards and legal requirements
- Preferred or alternative platforms
- External data sources
- Payment methods
- Compatibility with other products
- Latency and local hosting
