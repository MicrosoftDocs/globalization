---
title: Locale Model
description: Locale plays a vital role to develop the globalized software to be locale and culture aware.
ms.assetid: e65d446a-04fb-4235-859a-d84cbb64b463
ms.date: 02/23/2017
---
# Locale Model

Before deciding on an approach, you must first understand your design goals. Are you trying to change the language of the user interface or are you trying to present a locale-sensitive datum in the format the user expects? Locale-sensitive data are items such as date formats or sorted lists. Language and locale are related concepts, but are not interchangeable and there are sets of APIs to address each scenario.

There are several approaches to determining the language or locale, depending on whether you are working on web-based software or on a platform.

1.  Use the language/regional settings of the platform, whether it’s the operating system or software as a service (SaaS). An example of a SaaS that has language and regional setting is SharePoint.
2.  For a web app, you can use IP geolocation to find the user’s location and, based on that, guess the user’s language. This approach is labor intensive and doesn’t necessarily reflect the user’s desired settings. Some sites use this as the default, but allow the user to customize their settings.
3.  Alternatively for web apps, you could also process the [HTTP header Accept-Language](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) on the server side and extract the user’s language preferences based on their system’s language settings. This poses the risk of assuming the user wants their locale sensitive data to be displayed in the same format as their user interface language. It is recommended to ask the user for their preferred language and locale. From Windows 8, Edge, Internet Explorer 10 onward, the browser settings and operating system’s language values are identical.

For Windows 8 and greater, Windows provides users with the Windows’ Language Preference List. First the user selects a country or region. Then they may create an ordered list of the languages that the user is interested in working with. Users can add input capabilities, such as keyboards; change date-time settings; and choose which language to make their “primary” language (which is used as Windows Display (UI) language, once the corresponding language pack is downloaded). Users may further refine their locale settings by clicking on “Additional date, time & regional settings.”

You can access these settings using the [Windows.System.UserProfile.GlobalizationPreferences](https://msdn.microsoft.com/en-us/library/windows/apps/windows.system.userprofile.globalizationpreferences.aspx) class.

For developers on older systems, you will need to determine the user locale and the individual properties as documented for [National Language Support: Locales and Languages](https://msdn.microsoft.com/en-us/library/dd318716(v=vs.85).aspx).

## Keyboards and Other Input Methods

Most developers don’t need to worry what the user has set as their keyboard. Most modern programming languages pass through Unicode text to the consuming program. The exception may be for keyboard shortcuts. If you define a shortcut as Alt-S and there is no S on the keyboard, what does that mean for the user?

![Figure 1 Hindi Traditional Keyboard](/media/hubs/globalization/IC866727.png "Hindi Traditional Keyboard") *Figure 1 Hindi Traditional Keyboard*

If you do need to access the keyboard and its settings directly, <https://msdn.microsoft.com/en-us/library/ms646267(vs.85).aspx> provides this information.

## System Locale

If you are on an older system or need to support legacy programs, you may need to use the System Locale. The system locale determines which code page is used on the system by default on operating systems that use Unicode as their native encoding. Only applications that do not use Unicode as their default character-encoding mechanism are affected by this setting; therefore, applications that are already Unicode-encoded can safely ignore the value and functionality of this setting. As its name suggests, the system locale is a unique setting for each system. The system locale is a system variable that cannot be changed programmatically. The only way to change it is for an administrator to do so manually. More information about how to use this setting may be found at [SystemLocale](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/desktop/unattend/microsoft-windows-international-core-winpe-systemlocale).


