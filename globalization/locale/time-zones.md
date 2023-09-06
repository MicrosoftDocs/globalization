---
title: Time zones
description: Explore the complexities, including Daylight Saving Time, of time zones across the world.
ms.date: 06/13/2023
---

# Time zones

A time zone is a geographical region in which the same time is used. If the earth were to be divided into 24 time zones corresponding to the 24 hours in a day, each time zone would span 15° of longitude. However, because it's more convenient for areas to share time, time zone boundaries tend to follow country/region or administrative (for example, provincial or state) borders.

Even when a country’s width would suggest that more than one time zone would be used, countries and regions might elect to use fewer time zones. For example, China spans over 60° of longitude, but uses a single unified time zone (China Standard Time).

The time in any of the world's time zones can be expressed as an offset from a time standard called Coordinated Universal Time (UTC). UTC corresponds to the mean solar time at 0° of longitude. Most time zone offsets are typically in multiples of hours, but can be other combinations of hours and minutes, such as UTC+05:30 for India or UTC+05:45 for Nepal.

In addition to specifying time zone standards, countries and regions can also mandate the observation of Daylight Saving Time (DST). Daylight saving time tries to maximize daylight hours by advancing the time forward, typically by one hour, in the spring or early summer, and returning to the normal (or standard) time in the late summer or autumn. In practice, using DST means one 23-hour day in spring at the beginning of DST, and one 25-hour day in autumn at the end of DST. Each country or region can define the date and time of each transition. As summer in the Southern Hemisphere corresponds to winter in the Northern Hemisphere, the transition to DST in the Southern Hemisphere occurs around the same time that countries and regions in the Northern Hemisphere are transitioning back to standard time.

The transition to and from daylight saving time creates two kinds of anomalous times: invalid times and ambiguous times.

- An invalid time is a nonexistent time created by the transition from standard time to daylight saving time. For example, if the transition occurs on a particular day at 2:00 A.M. and causes the time to change to 3:00 A.M., each time interval between 2:00 A.M. and 2:59:59 A.M. is invalid.
- An ambiguous time is a time that can be mapped to two different times in a single time zone. It's created by the transition from daylight saving time to standard time. For example, if the transition occurs on a particular day at 2:00 A.M. and causes the time to change to 1:00 A.M., each time interval between 1:00 A.M. and 1:59:59 A.M. can be interpreted as either a standard time or a daylight saving time.

With differences in time zones, differences in the use of daylight saving time, and differences in the hour and date of transition between daylight saving time and standard time, converting times between time zones and date/time arithmetic across time zones can be complex. Fortunately, libraries like ICU, frameworks like .NET, and programming languages like Java help you handle calculations involving time zones. Supported features can include:

- Determining whether a time zone supports daylight saving time.
- Determining whether a given date/time is in daylight saving time.
- Converting date/times between different time zones.
