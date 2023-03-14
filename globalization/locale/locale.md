---
title: Locale
description: The combination of language and country or region names a locale.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/20/2023

---

# Locale

A locale is a collection of settings for the user's environment, such as language, country/region, and script. The user's locale allows the operating system or applications to use the appropriate conventions such as sort order; keyboard layout; and date, time, number, and currency formats.

Windows, and the APIs for creating applications, formerly used Language Code Identifiers (LCIDs) to specify locales, but newer versions of the APIs support BCP 47 locales. Note that LCIDs only covered a limited subset of the locales that can be defined by BCP 47. For more information about LCIDs, refer to [Other locale representations](other-locale-names.md).

Locale-related articles include the following:

- [Standard locale codes](standard-locale-names.md)
- [Other locale representations](other-locale-names.md)
- [Locale fallback](fallback.md)
