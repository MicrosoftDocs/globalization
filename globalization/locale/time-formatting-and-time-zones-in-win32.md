---
title: Time Formatting and Time Zones in Win32
description: 
ms.assetid: f468cc75-fdc5-4716-a42f-91df92b89401
ms.date: 03/16/2016
---


# Time Formatting and Time Zones in Win32

To format time in the default settings of a given locale or as specified by the user in the **Regional and Language Options** Control Panel, you can use GetTimeFormat. This function formats time—either a specified time or the local system time—as a time string for a specified locale.

The following code sample displays the current system time for the current user locale, using the default time format for that locale: 

```C++
// Formats time as a time string for a specified locale.
GetTimeFormat(LOCALE_USER_DEFAULT, // predefined current user locale
    0, // option flag for things like no usage of seconds or
     // force 24h clock
    NULL, // time - NULL to go with the current system locale time
    NULL, // time format string - NULL to go with default locale
     // format
    g_szBuff1, // formatted string buffer
    MAX_STR); // size of string buffer
```

Execution of this code would give the following result on English (United States) and Punjabi user locales, respectively. (See Figure 1 below)

![TimeFormat-Win32](/media/hubs/globalization/IC45886.jpg "TimeFormat-Win32") 

**Figure 1:** Time formatted for English (United States) and Punjabi user locales

As you saw in the previous example, the time formatting can be completely different from one locale to another. In this case, the use of a leading 0 in the hour representation, as well as the actual translation and positioning of P.M., change based on country and cultural standards. But even within the same locale or culture there is a variety of possible ways to format time: short or long formatting. The EnumTimeFormats function enumerates the time formats that are available for a specified locale. It does so by passing (to a callback function that an application defines) a pointer to a buffer that contains a time format. The EnumTimeFormats continues to do so until no more time formats are found, or until the callback function returns FALSE. Here is how the code works:

```C++
EnumTimeFormats(EnumTimeFormatsProc, // enumeration callback function
     LOCALE_USER_DEFAULT, // locale for which the enumeration is done
     NULL); // unused
 
    // The callback function...
    BOOL CALLBACK EnumTimeFormatsProc(LPTSTR lpTimeFormatString)
     {
     // end of enumeration, then terminate
     if (!lpTimeFormatString)
     return FALSE;
     MessageBox(NULL, g_lpTimeFormatString, TEXT("Available Time format"), MB_OK);
     return TRUE;
     }
```

Execution of this code would give the following result on English (United States) and French (France) user locales, respectively. (See Figure 2 below.)

![FrenchTimeFormat](/media/hubs/globalization/IC88253.jpg "FrenchTimeFormat") 

**Figure 2:** Time formats for English (United States) and French (France) user locales

The obtained result (format picture) can then be used as an lpFormat argument in a call to *GetTimeFormat*. This allows you to use an alternative formatting for the time. The following elements can be used to construct a format-picture string. (See Table 1 below.) If you use spaces to separate the elements in the format string, these spaces will appear in the same location in the output string. The letters must adhere to the casing conventions shown in the table. (For example, the correct formatting for "Seconds with leading zero for single-digit seconds" would be "ss" not "SS".) Characters in the format string that are enclosed in single quotation marks will appear in the same location and will be unchanged in the output string.

![](https://i-msdn.sec.s-msft.com/en-us/goglobal/bb688125.timepicStr(en-us,MSDN.10).jpg)

**Table 1:** Elements for constructing a format-picture string.

------------------------------------------------------------------------

For example, to get the time string:

```
"11:29:40 PM" 
```

use the following picture string:

```
"hh':'mm':'ss tt" 
```

To retrieve information regarding the time parameters for a particular time zone that the user has selected, you can use the GetTimeZoneInformation function. These parameters control the translations between UTC and local time.

```C++
DWORD GetTimeZoneInformation(LPTIME_ZONE_INFORMATION lpTimeZoneInformation);
// Where LPTIME_ZONE_INFORMATION is defined as:
typedef struct _TIME_ZONE_INFORMATION
    {
     LONG Bias;
     WCHAR StandardName[ 32 ];
     SYSTEMTIME StandardDate;
     LONG StandardBias;
     WCHAR DaylightName[ 32 ];
     SYSTEMTIME DaylightDate;
     LONG DaylightBias
    } 
    TIME_ZONE_INFORMATION, *PTIME_ZONE_INFORMATION;
```

The *Bias* parameter of the TIME\_ZONE\_INFORMATION structure is the difference, in minutes, between UTC time and local time.

All translations between UTC time and local time are based on the following formula:

```
UTC = local time + bias 
```

Unfortunately, Win32 APIs do not offer a solution to enumerate information relative to any other time zone than the one currently selected by the user. GetLocalTime and GetSystemTime will allow you to retrieve the current local and the UTC times, respectively. To convert the local time to UTC, you can use the LocalFileTimeToFileTime API. These are but two of the many Win32 APIs dealing with time. To learn about other functions, search for "time functions" on [http://msdn.microsoft.com.](http://msdn2.microsoft.com/)


