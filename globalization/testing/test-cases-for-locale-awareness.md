---
title: Test Cases for Locale Awareness
description: Globalization test cases for verifying the data in various regional settings.
ms.assetid: 7263c020-837b-478b-8c94-e59aeb913c8d
ms.date: 04/14/2017
---

# Test Cases for Locale Awareness

|**Areas and Items to Test**|**Details**|**Applicability**|
|---|---|---|
|Locale-independent data persistence|Applications must store and retrieve documents containing locale-sensitive data (such as the date, time, and numeric information); check that this data is stored in a locale-neutral form. It must be formatted for display purposes only and must follow the rules of the settings on the reviewer's system.|All applications that store data in an external persistent storage|
|Adherence to locale standards|Verify that locale-specific data (such as the time, date, currency, and numeric values) can be entered, interpreted, stored, and retrieved according to the rules set by the user locale. Specifically, verify that: A.M./P.M. symbols are not hard-coded for the time values; different time and date formats can be used, including different separators; dates in different calendars can be entered and edited; positive and negative number formats are recognized correctly; neither the dollar sign nor any other symbol is hard-coded as a currency symbol.|All applications|
|Dynamic usage of format separators|Verify that date, time, and numeric values are entered with data separators; make sure the separators are not hard-coded in the application, but rather are defined based on the current user-locale settings.|Applications that allow you to enter formatted data|
|Paper and envelope sizes|In accordance with the selected locale setting, check that applications pick the appropriate default paper and envelope sizes for correctly formatting information that's going to be printed. However, be sure to let the user override those settings. Verify that applications relay information about the proper default paper size to the printing device.|Applications that format printable information|
|Measurement-systems independence|Verify that applications that use real physical dimensions for formatting graphic and text data utilize the measurement system (metric or U.S. Customary System) corresponding to the user's locale settings.|Applications that use real physical dimensions for formatting graphic and text data|
