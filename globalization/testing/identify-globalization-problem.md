---
title: Identify Globalization Problem
description: The most serious globalization problem is functionality loss. This problem can surface when a system locale is changed, or when accessing input data.
ms.assetid: 022e7dc6-3be9-433b-8554-d356bdf751c1
ms.date: 04/03/2017
---

# Identify Globalization Problem

The most serious globalization problem is functionality loss. This problem can surface either immediately, such as when a language is changed, or later, such as when accessing input data (non-Latin character input).

Some functionality problems manifest themselves in the form of display problems. The following are some common ones that you might see:

-   Question marks (????) appearing instead of displayed text indicates problems in Unicode-to-code-page conversion.
-   Random characters (¼, «, †, ‰, ‡, ¶, and so on) appearing instead of readable text indicates that the code page-based code is using the wrong code page.
-   The appearance of default glyphs such as boxes, vertical bars, or tildes (random chars) indicates that the selected font cannot display some of the characters.

It might be hard to find certain problems in display or print results without having adequate shaping, layout, or script knowledge. Testing for these sorts of problems is language-specific and often cannot be executed without language expertise. On the other hand, this type of test might be limited to code inspection. For instance, if the text output is formed and displayed using standard text-handling mechanisms, such as DWrite for complex scripts (see "[Complex Scripts Awareness](https://msdn.microsoft.com/globalization/mt662335)"), complex-script processing in text output can be considered safe.

Another area of potential problems is code failing to follow locale conventions as defined by the language settings. Make sure that locale-sensitive data in your application (numbers, dates, time, currency, and calendars) is displayed according to the Language settings property sheet of your computer. (For information on locale awareness, see "[Locale and Cultural Awareness](https://msdn.microsoft.com/en-us/globalization/mt643089.aspx)." )

However, Language settings do not cover all locale-specific functionality. For example, you cannot see the current sort order there. Thus, it is important to have a test plan covering all aspects of functionality related to locale before you start your test. You can use the National Language Support (NLS) and the .NET Framework documentation as a starting point for this plan. Use this documentation for finding exactly what locale information you'll need to retrieve dynamically, and then apply those requirements to your project.

As a final note regarding globalized testing, when planning and running testing always remember that globalization is wider in scope than just supporting one particular language. The test you use to verify that code has been globalized might not seem to duplicate a realistic usage scenario; that is, the settings of a particular globalized test may look a bit unnatural. Think about cars being tested in extreme weather conditions. Obviously the deserts of Arizona in midsummer or the frozen Alaskan tundra in midwinter don't represent typical driving conditions. However, by covering the widest range of conditions possible, the test will produce more comprehensive results. Similarly, your test should cover the widest range of possibilities you can think of—including potential markets you might never have considered or even heard of, as well as the multiple ways in which your product might be used.

Once you've verified that a product's functionality has been globalized through globalizing the existing testing process, you will need to determine whether the application is going to be localized. If so, the next step is localizability testing. Using techniques such as pseudo-localization and the pseudo-mirroring test; reviewing code, UI, and documentation; and performing pilot localization are all tasks that comprise localizability testing.


