---
title: Parsing input
description: Learn how the context and the locale are crucial when parsing user input
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Parsing input

Applications consume text input in various ways, such as reading data files or users typing directly in text boxes. Text input can include data like numbers, dates, and times. It can be helpful to convert, or *parse*, the text input to a format that the application can use. For example, programming languages have data types to store integers, floating-point numbers, dates and times.

[Locales](../locale/locale.md) are a collection of settings for the user's environment, including the separators to be used for numbers, dates, and times. For example, in the US, the decimal separator is a period (.), and the grouping separator is a comma (,). In France, the decimal separator is a comma (,), and the grouping separator is a period (.). Users expect to interact with data using the separators that are appropriate for their locale. For example, `1.234` would represent `one thousand two hundred and thirty-four` in France, but `one and two hundred and thirty-four thousandths` in the US. When parsing numbers, you need to know the locale of the data to determine the separators used for grouping and decimals to be able to convert the text input to the correct value. As with formatting numbers, formatting dates, and formatting times, libraries like ICU, frameworks like .NET, and programming languages like Java have locale-aware methods that can assist with parsing and storing user input. Parsing dates and times have similar challenges to parsing numeric data, as the separators used to represent dates and times vary by locale; however, dates and times also have extra challenges, such as handling time zones and daylight saving time (DST). For more information, see [Parsing dates and times](#dates-and-times).

It's best practice to assume that numbers, dates, and times are entered in a format that corresponds to a format supported by the current application locale. For example, if a user inputs numeric data in France, the application might assume that a comma indicates a decimal separator. If the same data was inputted in the US, the application might assume that a comma indicates a grouping (thousands) separator. There are occasions where you might want to parse numbers, dates, and times with alternative locales. For example, an application that extracts numeric data from documents might be running with a locale setting of **French (France)**, but the user indicates that a document has a locale of **German (Germany)**. In this context, using the locale of the document might be more appropriate when parsing the numeric data.

If a user is entering data directly into an application via UI controls, it's best practice to use controls that restrict the type and format of data. For example, using a [date picker](/windows/apps/design/controls/date-picker) avoids having to determine the locale of the date entered by the user.

## List separation and CSV

In addition to the decimal separator and the grouping separator, Windows supports the *list separator*, which can be used as the default delimiter for applications to support formats like CSV. While CSV can support a delimiter that is the same as either the grouping or decimal separator, using a delimiter that is different than either the grouping or decimal separator is more common. When trying to read CSV data, an application needs to:

- determine the locale
- determine the delimiter used to separate values
- determine the separators used for grouping, decimal, dates, and times

## Parsing dates and times

Working with dates and times is more complex than working with numbers. Using C# as an example, there are structs and classes for [DateTime](/dotnet/api/system.datetime), [DateOnly](/dotnet/api/system.dateonly), [DateTimeOffset](/dotnet/api/system.datetimeoffset), etc. Each of these types has different properties and methods for parsing and formatting dates and times. For example, while both the [DateTime](/dotnet/api/system.datetime) struct and [DateTimeOffset](/dotnet/api/system.datetimeoffset) struct have Parse methods DateTimeOffset represents a date and time with an offset from UTC, while DateTime can represent a date and/or a time in a specific time zone, in Coordinated Universal Time (UTC), or using a specific calendar.

When parsing dates and times, you need to consider whether the date and time are absolute, or whether the date and time are relative to the current date and time:

- Does the time represent a recurring event, such as an alarm? Do you want the alarm to occur at the same time, regardless of your time zone or DST?
- Does the date and time represent a single meeting, where attendees in different time zones need to know the time of the meeting in their local time zone?
- Does the date and time represent a recurring meeting, where the time of the meeting might change depending on the local time zone and DST?
- Does the date and time represent a value in a log file, where the time zone and DST are irrelevant?
