---
title: Locale data and character sets
description: Formats of dates, time, currency, measurements, and telephone numbers vary from one locale to another.
ms.assetid: b2e3a5e7-bcea-4ea5-9c1e-8781c5fab435
ms.date: 03/16/2016
---

# Locale data and character sets

Formats of dates, time, currency, measurements, and telephone numbers vary from one locale to another.
Localizing the software to suit an international audience requires using the appropriate format for the particular locale.
You can change a format programmatically by using the globalization infrastructure provided in Windows operating systems and the .NET Framework.
(For more information, see [Locale and Culture Awareness](../locale/locale-and-culture.md).)
Some instances of locale-data values can be stored as part of the resources to initialize variables like the default character set or the default date format.
If the development team does indeed want to store these values, localizers should change the locale-value strings according to the format of the target locale.
