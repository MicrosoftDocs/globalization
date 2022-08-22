---
title: Choose a test platform
description: Globalization testing depends on the functionality of your system, required level of support, and the testers' ability to work on a localized OS.
ms.date: 04/03/2017
---

# Choose a test platform for globalization testing

Choosing the operating system for your globalized test is another important step.
Among the factors that can affect your decision are:

* the functionality of your system and required level of support,
* testers' ability to work on a localized version of the operating system,
* availability of the operating system for testing.

Even if you're targeting a broader range of operating systems, Windows can be a good fit as your primary test platform.
Windows gives you extensive flexibility to change language and locale settings, without having to install a different version of the OS.
Windows has native support for a broad range of languages and locales, and supports the addition of custom locales.
By adjusting the Windows language and locale settings, you can simulate varying language and regional environments on a single machine.

Even if the application hasn't been translated yet, you can begin testing its international regional support using pseudo locales.
Windows includes the three pseudo locales :::no-loc text="qps-ploc":::, :::no-loc text="qps-plocm":::, and :::no-loc text="qps-ploca":::.
The pseudo locales have been optimized for uncovering issues with the usage of locales in an application.
For more information on using pseudo locales, see [Pseudolocalization](../methodology/pseudolocalization.md).
  
You can also use multiple language support on Windows.
Multiple language support is especially useful if your code implements a multilingual UI and has to adjust to the UI settings of the operating system.
This approach is a more easily implemented alternative to installing multiple localized versions of the operating system.

Another test platform you can use is the localized build of the target operating system.
If the tested application is to be localized into certain languages, these languages are the obvious choice for the platform.
If the target operating system is Windows, other language versions of the operating system can be used too, even if the UI language doesn't match the language of your application.
By using this configuration, you check how your application interacts with a localized system.
In this configuration, names of the system folders, built-in accounts, fonts, and other system objects can be different.

Once you've chosen a test platform, the next step is to [create the test environment](create-the-test-environment.md).
