---
title: Units of Measurement
description: Most of world uses the metric system (meters, liters, grams, etc). Where the US still uses the imperial system (feet, inches, pounds, etc).
ms.assetid: 0889ecb8-4d4c-4dc2-b3ca-3c11cbf2b043
ms.date: 01/24/2017
---
# Units of Measurement

Throughout the world things are measured using different units and scales. The most popular one used is the metric system (meters, liters, grams, etc). Where as the US still uses the imperial system (feet, inches, pounds, etc). The kind of measurements referred to are for things such as:

-   Lengths
-   Weights
-   Area
-   Volume
-   Temperatures
-   Paper sizes
-   Angle notation
-   etc.

Thus you need to make sure that if you deal with measurements, you can display them in different systems. Also, make sure it is clear to the use on what system is currently being display. Remember a Mars probe was lost because it's guidance system was developed for one system and the scientists using it thought it was the other system.

### Units of Measurement in Win32

Although you need to do your own conversions between the metric and US systems, Win32 NLS APIs can help you detect which system of measurement is used for a given locale.

The system of measurement can be obtain from [GetLocaleInfo](https://msdn.microsoft.com/en-us/library/ms776270.aspx) API with [LCTYPE](https://msdn.microsoft.com/en-us/library/bb507201.aspx) flag set to *LOCALE\_IMEASURE*. The returned value is 0 if the metric system (Système International d'unités, or S.I.) is used, and 1 if the U.S. system is used. The maximum number of characters allowed for this string is two.

 ```C++
DWORD dwMSys;
GetLocaleInfo(LOCALE\_USER\_DEFAULT,     // locale identifier (current user locale)
LOCALE\_IMEASURE|LOCALE\_RETURN\_NUMBER, // information type (measurement system)
&dwMSys,                                 // retuned value
sizeof (DWORD));
```

### Units of Measurement in .NET Framework

The [RegionInfo](https://msdn.microsoft.com/en-us/library/system.globalization.regioninfo.aspx) class from the [System.Globalization](https://msdn.microsoft.com/en-us/library/system.globalization.aspx) namespace contains information about the country or region. In contrast to [CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx), RegionInfo does not represent preferences of the user and does not depend on the user's language or culture. A good example of this category of information is the [IsMetric](https://msdn.microsoft.com/en-us/library/system.globalization.regioninfo.ismetric.aspx) property of RegionInfo that gets a Boolean value indicating whether the country or region uses the metric system for measurements.


