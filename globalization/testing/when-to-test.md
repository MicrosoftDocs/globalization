---
title: When to test internationalized products
description: Using appropriate testing methods at the right time helps identify bugs before rework increases expense.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# When to test internationalized products

Releasing a product internationally involves more testing than you might realize. Developers know that each localized version needs to be tested, but there are also things you can do before getting to that stage. This "prelocalization testing," also known as localizability testing, aims to validate your code is properly internationalized.

The purpose of localizability testing is to verify that the user interface of the app can be easily translated to any target language without re-engineering or making code modifications. Since localizability bugs must be fixed in the code, they should be found as early during development as possible. This saves time later, as you don’t need to find and fix the same bugs for each target language. After localization has been carried out, the results are then checked in [localization testing](how-to-test.md).

However, some bugs and other issues may become more apparent after translations has been completed. The goal is to minimize the number and severity of issues found after translation, to reduce late rework, but is typically not a full substitute for validating localized versions.

There are four things you can do to reduce the impact of this fundamental problem.

1. [Review your code](#review-your-code).
1. [Review the source language UI and documentation](#review-the-source-language-ui-and-documentation).
1. [Test with a pseudolocalized version of your app](#test-with-a-pseudolocalized-version-of-your-app). If supporting right-to-left scripts, also test with a pseudomirrored version.
1. [Start localization with a small set of languages](#start-localization-with-a-small-set-of-languages).

## Review your code

Code reviews for internationalization can take place long before translation work. When reviewing your code, be sure it meets the following requirements:

1. Ensure that your UI can be translated efficiently and correctly. For a list of things to check, see [Localizability in What to look for when testing internationalized products](what-to-look-for-when-testing.md#localizability).
1. Ensure that your UI displays appropriately on screens with different resolutions and aspect ratios and that users can interact with the UI, for example, to input text with an [IME](../input/input-method-editors.md).

These can be done at the same time as reviewing your code for general internationalization, including:

1. Ensure that your text data isn't limited to a particular [script](../fonts-layout/writing-systems.md) or language (it might even be multilingual). The data should also work regardless of [locale](../locale/locale.md), [time zone](../locale/time-zones.md), or [units of measurement](../locale/measurement-units.md).
1. Ensure that you can display your text and UI in different scripts. You can input text in non-Latin scripts using [Input Method Editors (IME)](../input/input-method-editors.md).
1. Ensure that your app respects the conventions and settings of the OS. These include [locale](../locale/locale.md), [sort order](../locale/sorting-and-string-comparison.md), capitalization, folder names, and registry keys.
1. Ensure that your app respects the conventions of the target market. These include the formatting of names, [postal addresses](../locale/addresses.md), [phone numbers](../locale/telephone-numbers.md), and using the right [paper sizes](../locale/paper-size.md) and [units of measurement](../locale/measurement-units.md).
1. Ensure that your product is appropriate for the target market. This includes following local laws and regulations, using the preferred payment methods, and avoiding culturally sensitive issues. For more information, see [How to release products internationally](../methodology/how-to-release-products-internationally.md).

## Review the source language UI and documentation

You should ensure the terminology used in your app’s user interface and support documentation is clear, consistent, and unambiguous. Translators find it harder to do a good job if the UI and the documentation refer to the same thing with several different words, or if technical slang is used. The source text should also avoid nontechnical slang and culture-specific references.

## Test with a pseudolocalized version of your app

Pseudolocalization (informally, "pseudo") can be the most effective way of finding localizability bugs that would only be detected when translating your app. Pseudolocalization gives you a "translation" without the cost of producing one. You can create pseudolocalized resources using the [Multilingual App Toolkit](/windows/apps/design/globalizing/use-mat) or other translation tools. You can test a pseudolocalized version of your app anytime you would typically test its source language version. For general information on pseudolocalization, see [Pseudolocalization](../methodology/pseudolocalization.md).

Some localizability issues such as truncations, concatenation or strings that are not exposed to localization are easier to spot on a pseudolocalized version than on a real language. And unlike a real translated version, a pseudolocalized version is easy to use even if you don't understand other real languages.

Once you have pseudolocalized your product, [test it as you would a real language](how-to-test.md), covering both functional and visual aspects, paying special attention to [localizability issues](what-to-look-for-when-testing.md).

### Pseudomirroring

If you're planning to create a localized version of a product that supports a right-to-left writing system like Arabic or Hebrew, you should consider pseudomirroring testing, which you can implement as part of pseudolocalization. For an application targeted for these markets, you should follow the development and design rules outlined in [User interface layout](../fonts-layout/interface-layout.md) to allow for UI mirroring.

Pseudomirroring then verifies that these rules were followed. You can use pseudolocalization to generate resource files that contain right-to-left scripts. By using these resource files in conjunction with enabling mirroring in your application, you can test the mirroring behavior anytime you would typically test the source language version.

## Start localization with a small set of languages

Let’s assume that the product you want to release internationally is going to need localization into many different languages. For many people the instinctive solution is to release all those languages at the same time, or at least as many as possible. However, it might be more cost-effective to start with just one or two languages and add more in subsequent releases.

As discussed previously, [pseudolocalization](#test-with-a-pseudolocalized-version-of-your-app) can be extremely helpful, but it can never catch all issues. If you complete a validation through pseudolocalization (and address issues that have been found), then start the actual localization and localization testing with a small subset of pilot languages, you may identify additional issues before they impact your broader localization efforts. These typically include issues that specifically impact the translation process, ranging from tooling to challenges with the source text.

If you decide to start small, choose one or two languages for which you can easily organize localization and [localization testing](how-to-test.md). For instance, you might have experience with the language from previous projects, or your organization employs people who speak the language.

It's helpful to choose languages for which the localization is especially likely to expose localization problems. For example, with German, the translated text is likely to be longer and uses a different sentence structure. Arabic and Hebrew text is written from right-to-left and the UI for these languages should similarly be mirrored. Languages like Chinese and Japanese use a very large range of characters.

Every language is different, and localizing just one or two can't reveal every possible issue. Adding pseudolocalization and pilot localization may seem like extra steps that could slow down the pace of planned localized releases. When combined strategically, each step can significantly reduce the effort required in the next step, especially with a large number of target languages. This can not only reduce costs, it can also speed up the release of each planned language at the right quality by dramatically shortening its validation and bug fixing cycle.
