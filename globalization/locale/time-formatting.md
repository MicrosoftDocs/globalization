---
title: Time formatting
description: Each time displays the hour, minute, and second, but the presentation order and separators could vary in different countries/regions.
ms.assetid: f7194ac9-9c29-4f16-a38d-87ebab60888b
ms.date: 03/16/2016
---
# Time formatting

Like date and calendar formats, time formats are not constant throughout the world.
Although each representation of time basically displays the hour, minutes, and seconds, their presentation order and separators vary greatly.
In fact, there might be many differences between regions within the same country.
The time formatting might differ from one culture to another in one of the following three ways:

1. The use of either a 12-hour or 24-hour clock.

   Most European and Asian locales use the 24-hour clock compared to the 12-hour (AM/PM) model used in the United States.
   In 12-hour formats, the meridian indicator can be rendered in the language of the country, and can appear before or after the hour, depending on region.

2. The character used to separate hours, minutes, and seconds.

   Although the colon (:) is the character most used in separating the hours, minutes, and seconds, some Asian languages use ideographic characters.
   In addition, some locales require "h," "m," and "s" as part of the display.

3. The storage and display of time zones.

   One way that is frequently used to represent the time zone is to display UTC (Coordinated Universal Time) as the base, or the older GMT (Greenwich Mean Time).
   This is then followed by the time zone, which is indicated as a positive or negative offset from UTC in hours and minutes.
   You cannot assume a time zone offset is whole number of hours.
   Some time zones have 30-minute or 45-minute offsets.
   For example, the time zone for Bengaluru, India, would be displayed as UTC +5:30, and for Chatham Island, New Zealand, it would be UTC +12:45.
   Another way to display time zones is by using names for the local time zones.
   If you do so, you must take the following into account:

    - Not all countries use local names.

    - Time-zone abbreviations are not unique.

    - Not all countries use daylight saving time, and the transition moment varies by country/region.

    - One time zone might have many different names, depending on the country/region and the language.

> [!IMPORTANT]
> Changing the user locale or the locale variable does not adjust the time zone by default.

![Time formatting for Greek user locale](./images/Greek_Time.jpg "Time formatting for Greek user locale")

**Figure 1:** Time formatting for Greek user locale.

![Time zone and daylight saving time](./images/Time_Zone_DST.jpg "Time zone and daylight saving time")

**Figure 2:** Time Zone page of Date And Time Properties

## More information

- [Time Formatting and Time Zones in Win32](time-formatting-and-time-zones-in-win32.md)

- [Time Formatting and Time Zones in .NET Framework](time-formatting-and-time-zones-in-dotnet-framework.md)
