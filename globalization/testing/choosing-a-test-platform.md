---
title: Choosing a Test Platform for Globalization Testing
description: Globalization testing depends on the functionality of your system, required level of support, and the testers' ability to work on a localized OS.
ms.assetid: 43368161-d029-480c-9c71-67c1c26ae70d
ms.date: 04/03/2017
---


# Choosing a Test Platform for Globalization Testing

Choosing the operating system for your globalized test is another important step. Among the factors that can affect your decision are the functionality of your system and required level of support, testers' ability to work on a localized version of the operating system, and availability of the operating system for testing.

Even if you are targeting a broader range of operating systems, Windows can be a good fit for your primary test platform. This operating system gives you the flexibility with language and locale settings, in addition to native support for a broad range of languages and locales. In fact, by adjusting these settings, even when you run a localized application on an English version of Windows, the application will still behave as though it is running on a localized platform. Thus you can simulate varying language and regional environments on one machine, according to which language and locales you set.

You can also use other install language packs on English Windows. This is especially useful if your code implements a multilingual UI and has to adjust to the UI settings of the operating system. This approach is a more easily implemented alternative to installing multiple localized versions of the operating system.

Another test platform you can use is the localized build of the target operating system. If the tested application is to be localized into certain languages, these languages are the obvious choice for the platform. If the target operating system is Windows, other language versions of the operating system can be used too, even if the UI language does not match the language of your application. By using this configuration, you check how your application interacts with a localized system, where names of the system folders, built-in accounts, fonts, and other system objects might be different from what you get with an English or other language system. Once you've chosen a test platform, the next step is to create the test environment.


