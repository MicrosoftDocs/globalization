---
title: Locale and Culture Awareness
description: "To represent the data correctly, the software needs to be aware of the user's locale."
ms.assetid: 9b9cd170-03dc-48b9-aeee-c1a8e32f0559
ms.topic: navigation
ms.date: 03/16/2016
---

# Locale and Culture Awareness

[Locale](locale.md)  
A locale is a collection of settings for the user's environment, such as language, country/region, and script. The user's locale allows the operating system or applications to use the appropriate conventions such as sort order; keyboard layout; and date, time, number, and currency formats.

[Sorting and String Comparison](sorting-and-string-comparison.md)  
String sorting and comparison are language-specific. Even within languages based on the Latin script, there are different composition and sorting rules. Thus do not rely on code points to do proper sorting and string comparison.

[Calendar Differences](calendar-differences.md)  
The Gregorian calendar is used in most English speaking countries, but world-ready products should also take into consideration other calendaring systems in use worldwide.

[Date Formatting](date-formatting.md)  
Date formatting is not constant through out the world. Although each date basically displays the day, month, and year, their presentation order and separators vary greatly. In fact, there may be many differences between regions within the same country.

[Time Formatting](time-formatting.md)  
Like date and calendar formats, time formats are not constant throughout the world.

[Currency Formatting](currency-formatting.md)  
Currency formatting needs to take into consideration the currency symbol and symbol placement, and the number formatting display.

[Number Formatting](number-formatting.md)  
The number formatting deals with the character used as the decimal and thousands separators.

[Addresses](addresses.md)  
Various countries/regions have different address formats.

[Telephone Number](telephone-number.md)  
Like addresses, the format for telephone numbers around the world varies significantly. The input fields and the routines that process information dealing with telephone numbers should be able to handle the variety of formats.

[Paper Size](paper-size.md)  
It's important to set the paper size correctly if your application supports the print function.

[Units of Measurement](units-of-measurement.md)  
Throughout the world things are measured using different units and scales. The most popular one used is the metric system (meters, liters, grams, etc). Where as the US still uses the imperial system (feet, inches, pounds, etc).
