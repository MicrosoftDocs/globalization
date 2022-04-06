---
title: Identify globalization problems
description: The most serious globalization problem is functionality loss. This problem can surface when a system locale is changed, or when accessing input data.
ms.assetid: 022e7dc6-3be9-433b-8554-d356bdf751c1
---

# Identify globalization problems

The most serious globalization problem is functionality loss.
This problem can surface immediately, such as when a language or locale is changed.
Or, the problem might surface later, such as when accessing non-Latin character input.

Some functionality problems manifest themselves in the form of display problems.
The following are some common ones that you might see:

* Question marks (`?`) appearing instead of text can indicate using the wrong code page to convert text to Unicode.

* Random characters (¼, «, †, ‰, ‡, ¶, and so on) instead of readable text can also indicate that the wrong encoding is being used.

* The appearance of default glyphs (usually boxes) indicates that the selected font can't display some of the characters. This can be an issue with font selection, or an encoding issue.

* Truncated or overlapping text.

It might be hard to find certain problems in display or print results without having adequate shaping, layout, or script knowledge.
Testing for these sorts of problems is language-specific and often can't be executed without language expertise.
On the other hand, this type of test might be limited to code inspection.
If the text output is formed and displayed using system-provided text-handling mechanisms, such as DirectWrite for complex scripts, complex-script processing in text output can be considered safe.

Another area of potential problems is code failing to follow locale conventions as defined by the language settings.
Make sure that locale-sensitive data in your application (numbers, dates, time, currency, and calendars) is displayed according to the user's Regional settings.

However, Language and Regional settings don't cover all locale-specific functionality.
You can't see the current sort order there.
Thus, it's important to have a test plan covering all aspects of functionality related to locale before you start your test.
You can use the National Language Support (NLS) and the .NET Framework documentation as a starting point for this plan.
Use this documentation for finding exactly what locale information you'll need to retrieve dynamically, and then apply those requirements to your project.

When planning and running tests, remember that globalization is wider in scope than just supporting one particular language.
The test you use to verify that code has been globalized might not replicate a realistic user scenario.
The settings of a particular globalized test may look unnatural or extreme.
However, by covering a wide range of conditions, the test will produce more comprehensive results.
Similarly, your test should include potential markets you might not have considered or even heard of, and the multiple ways in which your product might be used.

Once you've verified that a product's functionality has been globalized by globalizing the existing testing, you'll need to determine whether the application is going to be localized.
If so, the next step is localizability testing.
