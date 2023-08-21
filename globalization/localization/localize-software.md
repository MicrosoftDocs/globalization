---
title: Localize software
description: Software and content localization each have their particular characteristics that drive different localization strategies.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/12/2023

--- 

# Localize software

When you design a software product, you need to consider the issues involved in localizing the product for other markets. This planning should be done early on to avoid unnecessary rework. This process of designing your software to be adaptable to different audiences with as few engineering changes as possible is known as internationalization. Internationalization is often abbreviated as i18n (the first and last letters, with 18 letters in between).

Some of these issues are more “technical” in nature and are common to all software localization projects. They include:

- [Separating translatable material](#separating-your-code-from-your-translatable-strings) from the rest of the code
- [Regional considerations](#regional-considerations) such as date and time formats, number formats, and address formats

Each software project also has some distinctive cultural aspects in addition to the common technical issues: how your software works for and supports users in different cultures, and which parts of it might need adaptation. These considerations include things like local holidays, name formats, and, most importantly, anything that might be confusing or inappropriate in some cultures.

## Separating your code from your translatable strings

Anything that users interact with in the UI might need to be adapted for use in other countries. This includes user-visible text (menus, dialog boxes, tooltips, messages, etc.), but can also include audio, images, and videos.

You should separate the translatable material from the rest of the code and send the translation vendor only what needs to be translated.

You can separate strings that should be translated by putting them in resource files. It's best practice for developers to store translatable strings in resource files that are separate from strings that shouldn't be translated, such as functional resources or debug resources. Functional resources include, for example, registry keys, function calls, and strings communicated between components.

Part of what you send to the translator might be marked as "Do not translate" in the translation memories or terminology lists. These entries might include product names, brand names, or API names. This can be handled automatically in many CAT tools if all non-translatable strings are marked as such in the source language resource files. You should decide on an approach for marking these strings. Depending on the resource file format, it might be a keyword that is inserted in the comment field or metadata that can indicate translate=no. Then your translation vendor can set up a rule in their CAT tool that parses all strings in your delivery, looking for the non-translatable indicator, and locks the strings that have it.

For more information, refer to [Externalize localizable resources](/globalization/localizability/externalize-resources).

## Regional considerations

This section introduces some localization-related issues that are discussed in more detail in separate topics.

### Date and time

Date and time formats vary by locale. For example, USA uses the month-day-year order for dates, while Germany uses day-month-year and Japan uses year-month-day. For more information, refer to [Calendars, date, and time](../locale/calendars.md).

### Numbers and currencies

Numbers can be treated differently in different locales. For example, the United States uses a period as a decimal separator, whereas France uses a comma. In the Netherlands, the currency symbol comes before the digits, while in Germany it appears after. For more information, refer to [Number formats](../locale/number-formatting.md) and [Currency formats](../locale/currency-formats.md).

### Address formats

In the US, postal addresses have a standard format that includes the state abbreviation. In Japan, the postal code appears first, with the recipient’s name appearing last. For more information, refer to [Postal address formats](../locale/addresses.md).

## Cultural considerations

As mentioned in the introduction, in addition to the more technical aspects of internationalization, you should always consider the purpose of your product and how it might be affected by adapting it to other markets and cultures. For example, if you're making educational software:

- School grade names might be different and the division of grades between primary and secondary schools might also differ.
- What is taught at each grade level might vary, or the same subject might be taught differently.
- The list of mandatory and optional subjects can vary by country or region.

Some common issues are discussed in the following sections.

### Avoiding cultural confusion or impropriety

You should consider whether any of your UI text strings, icons, interactive elements, or images might be confusing or even offensive to any of your target locales. This also goes for any examples and similar information shown to the user. Examples of potentially sensitive issues include:

- Emojis have different connotations for people of different cultures and even people of different ages within your own culture.
- Using the $ sign as a synonym for money or currency might be taken poorly in some countries.
- Gender-neutral language whenever possible can be helpful, as it lets you avoid any cultural blunders while also being inclusive towards people whose gender identity is nonbinary.
- Geography can be sensitive too. Consider how different countries and regions describe China and Taiwan, or the body of water called the Sea of Japan or the (Korean) East Sea. You need to decide how to handle such cases if your software uses maps.
- Humor, slang, and idioms can be touchy even within your own culture, let alone when localizing your software. Even though they can all be effective tools when they land right, it might be best to avoid them entirely, or at least consider their use carefully.
- If jokes and slang are difficult to localize properly, religion and politics can be even more so. Anything related to them merits careful consideration.

### Local holidays

National, religious, secular, and other holidays vary a great deal from one country to another. You should be careful if you're referring to them in your product in any way. This ties in with avoiding confusing or offending your target audience.

### Name formats

In most Western countries, a person’s given name or names appears before their family name when the full name is written out. However, in alphabetical lists the order is often reversed, with the family name coming first and being separated from the given name by a comma. In some Asian countries, for example, Japan, China, Korea, and Vietnam, the family name appears before the given name.

In a printed manual or webpage text, it's straightforward to instruct the translators to adapt people’s names for the target culture, which includes using the correct order of names. With software, it isn’t so simple. The UI of your product needs to be modified to adapt to different name formats depending on the culture.

### Payment methods

Some payment methods might be much less common in the target culture than in your own. They might even be entirely unavailable. The target culture can use a payment method that's not used in your culture. Research this area if your software can be used to make payments or handles the subject of payments in another way.

For more information, refer to [Payment methods](../internationalization/payment-methods.md).

### Third party data sources

Many of the concerns listed under Payment methods apply here too. If your software uses data sourced from a third party, you need to ensure the equivalent data is available for your target market. For example, if your software provides information about public transportation in Helsinki, Finland, you'll need to source similar data if you plan to release it to support public transportation in Tokyo, Japan.

## To sum it up

Any article like this can't be exhaustive. This article is meant to encourage you to think about how culture, country conventions, and simply the way of life around the world can affect the design of your product. It's better to design your product to be adaptable from the ground up instead of trying to “patch” these issues later.
