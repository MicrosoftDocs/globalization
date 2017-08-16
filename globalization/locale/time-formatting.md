---
title: Time Formatting
description: Each time displays the hour, minute, and second, but the presentation order and separators could vary in different countries/regions.
ms.assetid: f7194ac9-9c29-4f16-a38d-87ebab60888b
ms.date: 03/16/2016
---
# Time Formatting

Like date and calendar formats, time formats are not constant throughout the world. Although each representation of time basically displays the hour, minutes, and seconds, their presentation order and separators vary greatly. In fact, there might be many differences between regions within the same country. The time formatting might differ from one culture to another in one of the following three ways:

1.  The use of either a 12-hour or 24-hour clock.

    Most European and Asian locales use the 24-hour clock instead of the 12-hour A.M./P.M. model used in the United States. Also, A.M./P.M. can be rendered in the language of the country, and in some languages comes before the time and not after it.

2.  The character used to separate hours, minutes, and seconds.

    Although the colon (:) is the character most used in separating the hours, minutes, and seconds, some Asian languages use ideographic characters. In addition, some locales require "h," "m," and "s" as part of the display.

3.  The storage and display of time zones.

    One way that's frequently used to represent the time zone is to display GMT (Greenwich Mean Time) or its modern replacement UTC (Coordinated Universal Time) as the base. This is then followed by the time zone, which is indicated as a positive or negative offset in hours and minutes. (Some time zones use 30-minute or 45-minute offsets.) For example, the time zone for Bengaluru, India, would be displayed as UTC +5:30, and for Chatham Island, New Zealand, it would be UTC +12:45. Another way to display time zones is by using names for the local time zones. If you do so, you must take the following into account:

    -   Not all countries use local names.
    -   Time-zone abbreviations are not unique.
    -   Not all countries use daylight saving time, and daylight saving time does not start and end on the same day in every country.
    -   One time zone might have many different names, depending on the country and the language.

**Important:** Changing the user locale or the locale variable does not adjust the time zone by default.

![Time formatting for Greek user locale](/media/hubs/globalization/IC848903.jpg "Time formatting for Greek user locale") 

**Figure 1:** Time formatting for Greek user locale.

![Time zone and daylight saving time](/media/hubs/globalization/IC848902.jpg "Time zone and daylight saving time") 

**Figure 2:** Time Zone page of Date And Time Properties property sheet.

### See more info in the below links:
 - [Time Formatting and Time Zones in Win32](time-formatting-and-time-zones-in-win32.md)
 - [Time Formatting and Time Zones in .NET Framework](time-formatting-and-time-zones-in-dotnet-framework.md)



