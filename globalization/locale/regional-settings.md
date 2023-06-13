---
title: Regional settings and formats
description: Use regional settings to format date, time, numeric, and financial data for users in different countries.
ms.date: 06/13/2023
---

# Regional settings and formats

Regional settings influence how items like your [date/time](date-time-formats.md), [numeric](number-formatting.md), and [currency](currency-formats.md) data types appear when you apply formatting options. For example, a user in the USA might use forward slashes as a separator and the format month-day-year to enter a date value for a date/time field (for example, 8/29/2019); however, a user in Korea might see the same date using hyphens as a separator and using the format year-month-day (for example, 2019-08-29).

This principle also applies to numerical and financial data. Users in the United Kingdom will use the English pound symbol (£) to represent local currency in financial data, while users in Germany will use the Euro symbol (€).

Some regional settings, such as numerical, date, time, and calendar format, can be set via a user’s operating system but other regional conventions might need to be implemented by your application. These conventions include [postal address formats](addresses.md), [telephone number formats](telephone-numbers.md), and [units of measurement](measurement-units.md).

The collection of these settings is typically defined by a user’s [locale](locale.md), which is usually specified by parameters such as language, country/region, and script.
