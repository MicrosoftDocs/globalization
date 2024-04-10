---
title: Validating products for international release
description: An overview of issues related to globalization testing.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# Validating products for international release

When they start out, many software companies are focused on producing a single-language product. The people involved in the initial release aren’t focused on producing a multi-language app. The processes and timeline used to produce the single-language app might not be sufficient for delivering products in more than one language. The team responsible for testing and Quality Assurance (QA) are critical to ensuring that the functionality and appearance of the translated product is appropriate for the new target markets.

Ensuring world-readiness has a wider scope and requires more planning than just testing your app after the UI strings have been translated. The QA team must partner with the development team and project managers to determine the necessary criteria for globalization. Then the Quality Assurance (QA) process must make sure that those implicit requirements are met throughout design and development.

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

## What comes next

Once you verify that a product's functionality has been globalized by globalizing the existing testing, you need to determine whether the application is going to be localized. If so, the next step is **localizability testing**, discussed in [When to test internationalized products](when-to-test.md).  

After localizability testing is done, its findings implemented, and at least one or two languages have been localized, it’s time to carry out **localization testing**. For more information, see [How to test localized products](how-to-test.md).
