---
title: Format dates and times
description: Format date/time info based on region standards using locale-aware methods.
ms.date: 06/13/2023
---

# Format dates and times

To identify a unique point in time, you need to know the time, the date, and the time zone. This information can then be displayed to the user in various formats. Each country and/or region has standards or conventions for displaying dates and times.

## Date formats

Dates can be displayed in long and short formats. Differences in format can include:

- The name of an era based on the calendar system in use.
- An indicator for whether the year is earlier or later than the epoch for the calendar, such as BCE (before Common Era) when using the Gregorian calendar.
- The order of the year, month, and day information, for example:
  - South Korea – year-month-day
  - United States – month-day-year
  - Germany – day-month-year
- Four- and two-digit years. Note that two-digit years can lead to ambiguous dates.
- Month number or name. The month number can include or omit a leading zero. The month name can be an abbreviation or the full name.
- The number of the day within the month, with or without a leading zero.
- The use of a weekday name, as either a full name or abbreviation.
- Separators, commonly forward slashes, dashes or hyphens, or periods, but can be characters indicating year, month, and day.

## Time formats

Times can also be displayed in long and short formats. Differences in format can include:

- 12- and 24-hour time conventions.
- An indicator for ante meridiem and post meridiem when using a 12-hour time convention. This indicator can be an abbreviation, such as “AM” or “p.m.” and can be separated from the numeric values with a space.
- The number of the hour, with or without a leading zero.
- The number of the minute within the hour, with or without a leading zero.
- The inclusion of seconds and/or milliseconds, with or without a leading zero.
- Separators, commonly colons or periods, but can be characters indicating hour, minute, or second.
- The use of a time zone designator, typically the offset in hours and minutes from UTC (Coordinated Universal Time), or Z to indicate UTC.

[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) is a standard that defines a representation of dates, times, and UTC offset that can be used to specify a unique point in time. For example, 12:34 PM on January 2nd, 2002 in New York, United States, can be represented as 20020102T123400-0500. ISO 8601 also specifies formats for durations and time intervals.

## Other date/time considerations

ISO 8601 specifies that Monday is the first day of the week. However, Sunday and Saturday are also used as the first day of the week, depending on the country/region. Similarly, conventions for the weekdays/workweek and the weekend vary by country/region and can comprise one or two days, with Friday/Saturday or Saturday/Sunday being common combinations of weekend days.

When using 12-hour time conventions, there's no standard for representing midnight and noon. Noon can be displayed as 12:00 a.m., 00:00 p.m., or 12:00 p.m. To avoid ambiguity, consider using text to represent midnight and noon, or consider using a nearby time (11:59 p.m. or 12:01 a.m.) to indicate the start, middle, or end of a day.

The use of daylight-saving time creates two kinds of anomalous times: invalid times and ambiguous times. For more information about daylight-saving time and converting date/time between different time zones, see [Time zones](time-zones.md).

International Atomic Time (TAI) is measured using atomic clocks and is the basis for UTC (Coordinated Universal Time). Universal time (UT1) is calculated based on Earth’s rotation around the sun. The UTC standard allows for leap seconds to be added to compensate for the difference between TAI and UT1 due to irregularities and slowdown in the Earth’s rotation, such that the difference between UTC and UT1 is within 0.9 seconds. A leap second is reflected as a time of 23:59:60, prior to starting a new day.

## Using locale-aware methods for date/time formatting

Both .NET and Java permit storing date/time data as UTC, which allows for exchange of date/time information between systems. However, displaying date and time information depends on locale and context. Fortunately, libraries like ICU, frameworks like .NET, and programming languages like Java help you format dates and times.
