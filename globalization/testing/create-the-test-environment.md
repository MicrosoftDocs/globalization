---
title: Creating the test environment for globalization testing
description: Choosing a platform for the test is not enough to guarantee that the test is globalized and that no globalization problems are left in the code.
---

# Creating a test environment for globalization testing

Choosing a platform for testing is not enough to guarantee that the test is globalized and that no globalization problems are left in the code.
The static properties of the platform such as names of the system folders, built-in account names, and so on are only one part of the picture; you'll also need to consider those properties that can be manipulated.
For instance, you can configure language and cultural preferences of Windows through different settings of system and user locales.
You should tune these settings to exercise the potential problem areas of the application.

You can use the following test settings to detect some typical globalization problems.

This checklist gives you areas of functionality that you can test. along with showing you how they can be verified, the potential problems associated with them, and when the test is applicable.

For more information, see the [Sample International Testing Cases](sample-international-test-cases.md).

* **Non-Unicode data path cannot handle double-byte data properly.**

  The problems in this area can be detected if you select an East Asian system locale such as Japanese, Chinese, or Korean, and use data encoded with double-byte characters in the corresponding code page.

* **Components interacting with non-Unicode applications select incorrect code page (Windows versus OEM) for character conversion.**

  This problem can be detected with the system locale in cases where Windows and OEM encodings do not coincide.
  Locales like German or Russian are good candidates.
  The test data must contain characters whose code-point values are different in Windows and OEM code pages.

* **The component is unable to process and follow user-locale settings.**

  * Select the locales where special rules must be applied to functionality that your application exposes.
    For instance, for special sorting rules, select Turkish and test with dotless "I".
    For details, see [Globalize test data](globalize-test-data.md).
    Select Chinese for applications that support the multiple sort orders used in China (and use Chinese data).

  * For calendar processing, select locales with non-Gregorian calendars.

  * For date, time, number, and currency formatting, select locales with formatting rules different from those accepted in the environment where the application is developed.
  Try locales with different time and date separators. Programmers may assume the conventions for the locale they usually use.
  For example, the Italian (Italy) locale uses a period (.) as a time separator, while the Italian (Switzerland) locale uses a period as a date separator.
  In addition, make sure that data (such as files and databases) saved under one locale setting can be properly read and used under another locale, and that the data shown matches the client's settings.

  * Set the user locale different from the system locale.

* **For distributed applications, data is not successfully passed between different locales.**

  To detect this problem, set up a network with a mixed environment where some systems have an East Asian (for example, Japanese) system locale and others have a European system locale.
  Running the application in a mixed network verifies that data can be successfully passed between different locales.

  Test how your distributed system works when the time-zone settings are different among computers in your system.
