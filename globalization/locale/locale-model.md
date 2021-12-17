---
title: Locale model
description: Locale plays a vital role to develop the globalized software to be locale and culture aware.
ms.assetid: e65d446a-04fb-4235-859a-d84cbb64b463
ms.date: 02/23/2017
---
# Locale model

Before deciding on an approach to the locale model in your application, you must first understand your design goals.
Are you trying to change the language of the user interface or are you trying to present a locale-sensitive datum in the format the user expects
Locale-sensitive data are items such as date formats or sorted lists.
Language and locale are related concepts, but are not interchangeable and there are sets of APIs to address each scenario.

There are several approaches to determining the language or locale, depending on whether you are working on web-based software or on a platform.

- Use the language/regional settings of the platform, whether it’s the operating system or software as a service (SaaS).
  An example of a SaaS that has language and regional setting is SharePoint.

- For web apps, you could parse the [HTTP header Accept-Language](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) on the server side and extract the user’s language preferences based on their system’s language settings.
  This assumes the user wants their locale sensitive data to be displayed in the same format as their user interface language.
  It is recommended to ask the user for their preferred language and locale.

- For a web app, you could use IP geolocation to find the user’s location and based on that, guess the user’s language.
  This approach is labor intensive and doesn’t necessarily reflect the user’s preference.
  Some sites use this as the default, but allow the user to customize their settings.

For Windows 8 and greater, Windows provides users with the Windows’ Language Preference List.
First the user selects a country or region.
Then they may create an ordered list of the languages that the user is interested in working with.
Users can add input capabilities, such as keyboards; change date-time settings; and choose which language to make their “primary” language (which is used as Windows Display user interface language, once the corresponding language pack is downloaded).
Users may further refine their locale settings by clicking on “Additional date, time & regional settings.”

You can access these settings using the [Windows.System.UserProfile.GlobalizationPreferences](/uwp/api/Windows.System.UserProfile.GlobalizationPreferences) class.

For developers on older systems, you will need to determine the user locale and the individual properties as documented for [National Language Support: Locales and Languages](/windows/win32/intl/locales-and-languages).

## Keyboards and other input methods

Most developers don’t need to worry what the user has set as their keyboard.
Most modern programming languages pass through Unicode text to the consuming program.
The exception may be for keyboard shortcuts.
If you define a shortcut as Alt-S and there is no S on the keyboard, what does that mean for the user?

Consider the keyboard in Figure 1:

![Figure 1 Hindi Traditional Keyboard](/media/hubs/globalization/IC866727.png "Hindi Traditional Keyboard") *Figure 1 Hindi Traditional Keyboard*

If you do need to access the keyboard and its settings directly, see [About Keyboard Input](/windows/desktop/inputdev/about-keyboard-input).

## System locale

If you are on an older system or need to support legacy programs, you may need to use the System Locale.
The system locale determines which code page is used on the system by default on operating systems that use Unicode as their native encoding.
Only applications that do not use Unicode as their default character-encoding mechanism are affected by this setting; therefore, applications that are already Unicode-encoded can safely ignore this setting.
As its name suggests, the system locale is a unique setting for each system.
The system locale is a system variable that cannot be changed programmatically.
The only way to change it is for an administrator to do so manually.
More information about how to use this setting may be found at [SystemLocale](/windows-hardware/customize/desktop/unattend/microsoft-windows-international-core-winpe-systemlocale).
