---
title: Units of measurement
description: Most of world uses the metric system (meters, liters, grams, etc.). Where the US still uses the imperial system (feet, inches, pounds, etc.)
ms.assetid: 0889ecb8-4d4c-4dc2-b3ca-3c11cbf2b043
ms.date: 01/24/2017
---
# Units of measurement

Throughout the world things are measured using different units and scales.
The most commonly used is the metric system (meters, liters, grams, etc.), whereas the US still uses the imperial system (feet, inches, pounds, etc.), except for certain industries and fields of science.
Since it is mainly the US that uses this system, we will refer to it as the US system.

The kind of measurements referred to are for things such as:

- Lengths
- Weights
- Area
- Volume
- Temperatures
- Paper sizes
- Angle notation
- etc.

Thus you need to ensure that if you deal with measurements, you can display them using different systems.
Also, make sure it is clear to the user what system is currently being displayed.

In 1999, the NASA Mars Climate Orbiter was lost on entry to the Martian atmosphere because of "the failed translation of English units into metric units" (see [MARS CLIMATE ORBITER FAILURE BOARD RELEASES REPORT](https://science.ksc.nasa.gov/mars/msp98/news/mco991110.html)).

## Units of measurement in Win32

Although you need to do your own conversions between the metric and the US systems, Win32 NLS APIs can help you detect which system of measurement is used for a given locale.

To determine the measurement system, use [GetLocaleInfoEx](/windows/desktop/api/winnls/nf-winnls-getlocaleinfoex) API with [LCTYPE](/windows/desktop/Intl/locale-information-constants#constants-used-in-the-lctype-parameter-of-getlocaleinfo-getlocaleinfoex-and-setlocaleinfo) flag set to LOCALE\_IMEASURE.
The returned value is 0 if the metric system (Système International d'unités, or S.I.) is used, and 1 if the US system is used.
The maximum number of characters allowed for this string is two.

 ```cpp
DWORD dwMSys;
GetLocaleInfo(LOCALE_USER_DEFAULT,      // locale identifier (current user locale)
  LOCALE_IMEASURE|LOCALE_RETURN_NUMBER, // information type (measurement system)
  &dwMSys,                              // returned value
  sizeof (dwMSys) / sizeof(TCHAR));
```

## Units of measurement in .NET

The [RegionInfo](/dotnet/api/system.globalization.regioninfo) class from the [System.Globalization](/dotnet/api/system.globalization) namespace contains information about the country or region.
In contrast to [CultureInfo](/dotnet/api/system.globalization.cultureinfo), RegionInfo does not represent preferences of the user and does not depend on the user's language or culture.
A good example of this category of information is the [IsMetric](/dotnet/api/system.globalization.regioninfo.ismetric) property of RegionInfo that gets a Boolean value indicating whether the country or region uses the metric system for measurements.
