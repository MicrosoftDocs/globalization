---
title: The World-Ready Approach to Testing
description: World-ready testing reduces redundancy in test runs on localized products and make simultaneous release possible.
ms.assetid: a6b10a4c-a8b4-4ccb-9c1e-d5f82adcacc0
ms.date: 04/03/2017
---

# The World-Ready Approach to Testing

Single code-base design, unified data-processing algorithms, and elimination of functionality problems due to localization are some of the benefits of software globalization. These benefits, which were not possible with former development methods, reduce redundancy in test runs on localized products and make simultaneous release possible.

The old approach to international testing was extensive and often inefficient, as was international software development. If you wanted to double the number of supported languages or locales, you could end up doubling the resources spent on development and testing. Even if the settings for the two locales were similar, you could not assume the application would work for one locale just because it worked for another.

By globalizing the functionality test, however, you can make testing easier and more efficient. Once you know the application is globalized, you know it supports any locale and any language. Unlike older test processes, the world-ready approach renders unnecessary the software development concept called "enabling." When done correctly, all world-ready applications are enabled to handle all the languages that are supported by the underlying platform. Thus, instead of having to test functionality for each localized version of an application, by globalizing the functionality test you verify that functionality has been globalized for the core product. Even though global functionality is available in a single, world-ready binary, localized products are still in demand in their respective markets, and thus still need to be built and tested. What is different is the focus of localization testing. Now you only need to check how well the product was adapted for a given locale or language, which allows you to verify that localization does not break globalized and localizable resources. Since this adaptation mostly involves translation, localization testing requires only limited technical expertise; instead, language proficiency becomes the major requirement for the tester. (See [Localization Testing](https://msdn.microsoft.com/en-US/library/mt662422).)

In addition to making localization testing, the entire localization process in general becomes less complex and requires fewer resources. This is yet another of the many advantages that software developers gain by creating a single, world-ready binary. (See [Design for Internationalization](https://msdn.microsoft.com/globalization/mt790752).) The following list is just a few examples of how the localization process becomes more efficient:

-   Localization teams are less likely to find localizability problems in multiple language versions that might require multiple fixes and branches of source code.
-   Since the localization process becomes mostly user interface (UI) translation, localized product testing becomes less technical and more a matter of checking grammar and spelling.

But before localizers can start their work for the very first target language, those responsible for testing must verify that the application is globalized and localizable (world-ready). **Figure 1** shows the steps needed-from a testing perspective-to ship a world-ready and localized (internationalized) product. While the figure necessarily omits the many details of a world-ready development process, and while the actual sequence of tasks might differ sometimes, it assembles the major components of this article in their logical order. Most importantly, the figure reinforces some key ideas about globalizing the QA process:

-   Multilingual sim-ship of software is possible if core development and testing meet world-ready criteria.
-   Should you decide to localize, the localizability test should be performed in parallel with the globalized functionality test.
-   Localization must start as soon as the code is stable enough, and only after the initial localizability test.

![Testing process required for shipping an internationlized product](/media/hubs/globalization/IC10646.gif "Testing process required for shipping an internationlized product") 

**Figure 1** - Testing process required for shipping an internationalized product.

Another key implication of globalization-and globalized testing-is the ability to expand the target market after the product is shipped. Thus, even if supporting a locale or language was not on your mind when the application was developed, you can re-evaluate later and move to a new market without changing the code. Globalized testing performed in the development cycle will ensure there are no serious problems with this move. Of course, some basic language-specific or locale-specific verification is required, but the amount can be significantly reduced compared to what was needed before releasing a language-specific application. When properly conducted, globalized testing will decrease the number of bugs, help you use resources more efficiently, and reduce costs down the road. The [next section](https://msdn.microsoft.com/globalization/mt662415) will show you how to prepare and carry out an effective globalized test that guarantees the globalization of the application, and will also discuss some common globalization problems.


