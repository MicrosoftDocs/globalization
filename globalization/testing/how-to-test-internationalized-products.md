---
title: Validating products for international release
description: An overview of issues related to globalization testing.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# Validating products for international release

Ensuring world-readiness has a wider scope and requires more planning than just testing your app after the UI strings have been translated.

When they start out, many software companies are focused on producing a single-language product. The people involved in the initial release aren’t focused on producing a multi-language app. The processes and timeline used to produce the single-language app might not be sufficient for delivering products in more than one language. The team responsible for testing and Quality Assurance (QA) are critical to ensuring that the functionality and appearance of the translated product is appropriate for the new target markets.

The Quality Assurance (QA) process is ideally a partnership between the development team, project managers, and other functions. The goal is to establish clear criteria for international release and verify that these are met throughout the product lifecycle, including design, development, distribution, and support.

## Common globalization issues

Software design and development can easily break world-readiness when:

- Legacy single-language methods, thinking, and practices are used.
- International conventions aren't considered.
- Text layout and other text properties aren't designed for.

The most serious globalization problem is functionality loss. This problem can surface immediately, such as when a language or locale is changed. It might also surface later, such as when accessing non-Latin character input.

Some functionality problems manifest themselves in the form of display problems. The following are some common ones that you might see:

- Question marks (?) or random characters (¼, «, †, ‰, ‡, ¶, and so on) appearing instead of text can indicate an issue [converting text](../text/encoding_text_conversion.md) from one code page to another.
- The appearance of default glyphs (usually boxes) indicates that the selected font can't display some of the characters. This can be an issue with font selection or another encoding issue.
- Text appears truncated or overlapping.

It might be hard to find certain problems in display or print results without having adequate layout, script, or shaping knowledge. Testing for these sorts of problems is language-specific and often can't be executed without language expertise.

## Locale-related issues

Another area of potential problems is code failing to follow [locale](../locale/locale.md) conventions as defined by the language settings. Make sure that locale-sensitive data in your app ([numbers](../locale/number-formatting.md), [dates, time](../locale/date-time-formats.md), [currency](../locale/currency-formats.md), and [calendars](../locale/calendars.md)) respects the user’s **Region** settings.

However, **Language** and **Region** settings don’t cover all locale-specific functionality. You can’t see the current sort order there, for example. Thus, it's important to have a test plan covering all aspects of functionality related to locale before you start your test. You can use the [.NET Framework documentation](/dotnet/api/system.globalization.cultureinfo) as a starting point for this plan. Use the documentation to find exactly what locale information you need to retrieve dynamically, and then apply those requirements to your project.

When planning and running tests, remember that globalization is wider in scope than just supporting one particular language. The test you use to verify that code has been globalized might not replicate a realistic user scenario. The settings of a particular globalized test might look unnatural or extreme. However, by covering a wide range of conditions, the test produces more comprehensive results. Similarly, your test should include potential markets you might not have considered or even heard of, and the multiple ways in which your product might be used.

## Test tools

Test tools, especially automated tools, play an essential role in the testing process. While automated testing can't completely replace manual testing, many test areas gain tremendous benefits from automation. For instance, using automated test tools is an effective way to verify the functionality of a localized product. Automated tests can validate the degree of a product's globalization.

Running automated tests on the original and localized applications side by side can verify that localization doesn't break any functionality. With automation, you don't need to understand the language of the localized UI since the tools can test the functionality regardless of the language. For instance, "Select the default button" is a test of functionality that can work for any language.

Ensuring that a product is globalized requires the ranges of test input to be extended, and environment settings to be more diverse. Automation makes it easier to deal with the additional test cases and allows you to efficiently track the results. Restoring the locale settings or test input that brought about an error in a program also becomes easier.

### Globalized test tools

Automation of test runs involves more than just running your usual test tools on your new product under a globalized environment. Test tools that check the functionality of your app UI can be broken when the tested application is translated. Even when not affected by translation, test results might be incorrect if the tool verifies locale-formatted data and assumes that the data format is fixed. For example, in globalized applications, the date format varies according to [locale](../locale/locale.md) and [region](../locale/regional-settings.md). The inability to use international test data can make a test tool unusable.

To avoid these and similar problems, developers of test tools must follow the same rules as the developers of globalized software do. Test tools must be globalized, adjust themselves dynamically to locale settings, and process international text data. If they must access localizable objects by name, the test tools must also be localized.

Experience shows that some tools are easy to globalize, while others aren't. More advanced programming models usually provide better ways to make the code universal regarding locale and language settings.

## What comes next

Once you verify that a product's functionality has been globalized by globalizing the existing testing, you need to determine whether the application is going to be localized. If so, the next step is **localizability testing**, discussed in [When to test internationalized products](when-to-test.md).  

After localizability testing is done, its findings implemented, and at least one or two languages have been localized, it’s time to carry out **localization testing**. For more information, see [How to test localized products](how-to-test.md).
