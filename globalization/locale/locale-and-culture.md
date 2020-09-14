---
title: Locale and Culture
description: 'To represent the data correctly, the software needs to be aware of the user's locale.'
ms.assetid: 9b9cd170-03dc-48b9-aeee-c1a8e32f0559
ms.date: 03/16/2016
---
# Locale and Culture Awareness

[Using Locale Model](https://docs.microsoft.com/globalization/locale/locale-model)  
To represent the data (number, currency, etc.) correctly, the software needs to be aware of the user's locale. To create software that is locale and culture aware, you'll need to understand what the term "locale" means, as well as the role locale variables play in the development process.

[Sorting and String Comparison](https://docs.microsoft.com/globalization/locale/sorting-and-string-comparison)  
String sorting and comparison are language-specific. Even within languages based on the Latin script, there are different composition and sorting rules. Thus do not rely on code points to do proper sorting and string comparison.

[Calendar Differences](https://docs.microsoft.com/globalization/locale/calendar-differences)  
The Gregorian calendar is used in most English speaking countries, but world-ready products should also take into consideration other calendaring systems in use worldwide.

[Date Formatting](https://docs.microsoft.com/globalization/locale/date-formatting)  
Date formatting is not constant through out the world. Although each date basically displays the day, month, and year, their presentation order and separators vary greatly. In fact, there may be many differences between regions within the same country.

[Time Formatting](https://docs.microsoft.com/globalization/locale/time-formatting)  
Like date and calendar formats, time formats are not constant throughout the world.

[Currency Formatting](https://docs.microsoft.com/globalization/locale/currency-formatting)  
Currency formatting needs to take into consideration the currency symbol and symbol placement, and the number formatting display.

[Number Formatting](https://docs.microsoft.com/globalization/locale/number-formatting)  
The number formatting deals with the character used as the decimal and thousands separators.

[Addresses](https://docs.microsoft.com/globalization/locale/addresses)  
Various countries/regions have different address formats.

[Telephone Number](https://docs.microsoft.com/globalization/locale/telephone-number)  
Like addresses, the format for telephone numbers around the world varies significantly. The input fields and the routines that process information dealing with telephone numbers should be able to handle the variety of formats.

[Paper Size](https://docs.microsoft.com/globalization/locale/paper-size)  
It's important to set the paper size correctly if your application supports the print function.

[Units of Measurement](https://docs.microsoft.com/globalization/locale/units-of-measurement) 
Throughout the world things are measured using different units and scales. The most popular one used is the metric system (meters, liters, grams, etc). Where as the US still uses the imperial system (feet, inches, pounds, etc).
