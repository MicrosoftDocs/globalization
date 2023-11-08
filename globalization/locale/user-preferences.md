---
title: Identifying user preferences
description: How to identify preferences of international users for user interface, input, and content, including language and regional formats.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 10/25/2023

---
# Identifying user preferences

Products intended for international markets need to be able to identify and follow users’ language and country preferences. Windows has a dedicated group of settings for this purpose under **Settings** > **Time & language** > **Language & region**. They consist of:

- **Windows display language**: used for the Windows UI and for features such as File Explorer
- **Preferred languages**: a Microsoft Store application uses the first language in this list that is supported by the app
- **Country or region**: Windows and applications can use this setting to customize the content that is presented to the user
- **Regional format**: Windows and apps use this setting to format dates and times according to the conventions of the selected locale

All Windows language settings are available via [.NET API's CultureInfo Class](/dotnet/api/system.globalization.cultureinfo).

In addition to the operating system settings, browsers have their own language settings. In Microsoft Edge, they're found under **Settings** > **Languages**. Microsoft Edge has its own preferred languages list for displaying websites, when using browser-based applications, and using writing assistance tools. You can also display Microsoft Edge in any of the languages on this list.

## User preferences in your applications

Ideally, your application should be using the first match in the **Preferred languages** list to either set the UI language of the application or the default UI language of the application. The difference between the two matters if your application has a setting that lets users select the language just for that application.

In some cases, it might be better for your application to use the Windows display language, rather than the **Preferred language**. This might be the case when your application is in integrated within Windows, for example, a printer driver or volume control utility.

If your application relies on region-specific data sources, such as local news or timetables, it could refer to the **Country or region** setting.

The **Regional format** settings usually reflect the **Windows display language** or **Preferred language** choice; however it’s not mandatory. Formatting of times and dates, numbers, currencies, and so on, should use the **Regional format** settings, not the UI language specified by the **Preferred language** or the **Windows display language**.

If your application is an in-browser experience, it should respect the language settings available in the browser.

## Fallback for unsupported languages

Sometimes there might not be an exact match between the language and region the user has selected and what your application supports. In these situations, Windows uses a fallback mechanism to pick the best possible option from the available ones.

For example, if a user has set the first **Preferred language** in Windows to Spanish (Argentina), but your application only supports Spanish (Spain) and English (United States), then Spanish (Spain) resources are used as it's a closer match to Spanish (Argentina).

Fallback scenarios are discussed in more detail in [Locale fallback](fallback.md).
