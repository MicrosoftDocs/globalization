---
title: Creating the Test Environment for Globalization Testing
description: Choosing a platform for the test is not enough to guarantee that the test is globalized and that no globalization problems are left in the code.
ms.assetid: e2e060ec-90da-4f42-a4a4-4b9374c33276
ms.date: 03/16/2016
---

# Creating the Test Environment for Globalization Testing

Choosing a platform for the test is not enough to guarantee that the test is globalized and that no globalization problems are left in the code. The static properties of the platform (such as names of the system folders, built-in account names, and so on) are only one part of the picture; you'll also need to consider those properties that can be manipulated-in other words, the platform's dynamic properties. For instance, you can configure language and cultural preferences of Windows through different settings of system and user locales. You should, in fact, tune these settings for the best outcome of your test. While this article has identified general areas of specific functionality to target, you have not yet seen how to target them. Therefore, the following list digs deeper into those areas, giving you optimal test settings to use for detecting some typical globalization problems. (For more information, see the "[Sample International Testing Cases] (https://msdn.microsoft.com/globalization/mt662424 "Sample International Testing Cases")." This checklist gives you further areas of functionality that you can test, along with showing you how they can be verified, the potential problems associated with them, and when the test is applicable.)

**Non-Unicode data path cannot handle double-byte data properly.** The problems in this area can be detected if you select an East Asian system locale such as Japanese, Chinese, or Korean, and use data encoded with double-byte characters in the corresponding code page.

**Components interacting with non-Unicode applications select incorrect code page (Windows versus OEM) for character conversion.** This problem can be detected with the system locale in cases where Windows and OEM encodings do not coincide. European locales, like German or Russian, are good candidates. The test data must contain characters whose code-point values are different in Windows and OEM code pages.

**The component is unable to process and follow user-locale settings.** Select the locales where special rules must be applied to functionality that your application exposes. For instance, for special sorting rules, select Turkish (test with dotless "I"). For details, see "[Globalizing Your Test Data](https://msdn.microsoft.com/en-us/globalization/mt662420 "Globalizing Your Test Data")". Select Chinese for applications with different sort orders (and use Chinese data).

For calendar processing, select locales with non-Gregorian calendars. Finally, for date, time, number, and currency formatting, select locales with formatting rules different from those accepted in the environment where the application is developed. Try locales with different time and date separators, since too often programmers assume the colon or slash to be the only possibilities. For example, the Italian (Italy) locale uses a period (.) as a time separator, while the Italian (Switzerland) locale uses a period as a date separator. In addition, make sure that data (such as files and databases) saved under one locale setting can be properly read and used under another locale, and that the data shown matches the client's settings.

It is also a good idea to set the user locale different from the system locale. A non-Unicode component will fail to display when all of the following are true:

-   Your application picks an incorrect locale for data formatting.
-   The mechanisms used to display locale-specific data treat text as Unicode.
-   The date or time has to be displayed using symbols not in the current code page.

Having a non-Unicode component that fails to display is as bad as picking an incorrect format.

**For distributed applications, data is not successfully passed between different locales.** To detect this problem, set up a network with a mixed environment where some systems have an East Asian (for example, Japanese) system locale and others have a European system locale. Having the application run in a distributed, mixed network verifies that data can be successfully passed between different locales. Additionally (though not really within the scope of globalization), it might also be wise to test how your distributed system works when the time-zone settings are different among computers in your system.

You've determined which code, components, and applications are most likely to present globalization problems, decided upon a test platform, and manipulated settings to create an optimal testing environment for detecting specific problems. Following the guidelines just presented will ensure you have considered vital issues when preparing to carry out a globalized test.


