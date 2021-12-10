---
title: Handling calendars in Win32
description: As you probably noticed in the last code sample, one of the arguments of the enumeration callback function for date formats is the calendar type (CALID).
ms.assetid: dc16dec7-abcd-4b26-84d8-c229a5853329
ms.date: 03/16/2016
---
# Handling calendars in Win32

> [!NOTE]
> Examples in this topic use LCID to identify locales.
> Microsoft has been migrating toward the use of locale names instead of locale identifiers since Windows Vista.
> Any application that runs only on Windows Vista and later should use the ...Ex versions of most NLS APIs,
> which use a locale name to identify a locale instead of an LCID.
> See [Locale names and LCID deprecation](locale-names.md) for more information.

As you probably noticed in the last code sample, one of the arguments of the enumeration callback function for date formats is the calendar type (CALID).
As mentioned earlier, for some locales more than one calendar type is available.
For example, if the user locale is set to Hebrew, then the enumeration would return long-date formats for both Gregorian and Hebrew lunar calendars.
For most of the applications, the basic functionality made available by [GetDateFormatW](https://docs.microsoft.com/windows/win32/api/datetimeapi/nf-datetimeapi-getdateformatw), which allows the date to be represented in the currently selected calendar and format, is enough.
However, some applications might want to have more control over the way this information is presented and eventually select the calendar type in which the date is being displayed.
There are several Win32 NLS APIs that allow you to manipulate calendar types.

The [EnumCalendarInfoEx](https://docs.microsoft.com/windows/win32/api/winnls/nf-winnls-enumcalendarinfoexw) API can be used to enumerate all calendar information (such as names of calendars, names of days of the week, and names of months) for all applicable and available calendar types pertaining to a given locale.
The code sample enumerates the native names of all supported calendars.

```cpp
// Enumerate the native calendar names for all available calendar
// types that correspond to the current user locale.
EnumCalendarInfoEx(EnumCalendarInfoProc,   // enumeration callback
// function
LOCALE_USER_DEFAULT,   // locale - any valid LCID
ENUM_ALL_CALENDARS,    // does enumeration for all supported

// calendars
CAL_SCALNAME); // calendar info (return the calendar name)
// The callback function will look like:
BOOL CALLBACK EnumCalendarInfoProc(LPTSTR lpCalendarInfoString, CALID Calendar)
{
    if (!lpCalendarInfoString)
        return FALSE;
    MessageBox(NULL, g_szBuf2, TEXT(&Calendars names&), MB_OK);
    return TRUE;
}
```

Execution of the previous code sample would give the following result on English (United States) and Arabic (Tunisia) user locales, respectively.

![Available calendar types for English (US) and Arabic (Tunisia)](./images/Calendar_Types.jpg "Available calendar types for English (US) and Arabic (Tunisia)") 

**Figure 1.** Available calendar types for English (United States) and Arabic (Tunisia)

The [GetLocaleInfo](https://docs.microsoft.com/windows/win32/api/winnls/nf-winnls-getlocaleinfow) API with the LOCALE\_ICALENDARTYPE flag also allows you to retrieve the default calendar type currently selected by the user.
Once you have retrieved the calendar you want, you can use [GetCalendarInfo](https://docs.microsoft.com/windows/win32/api/winnls/nf-winnls-getcalendarinfow) to retrieve specific information about that particular calendar.
This information includes the following:

- Long, short, and year/month date formats
- Abbreviations and full names of months
- Abbreviations and full names of days of the week
- An integer value indicating the upper boundary of the two-digit year range
- Native name of the calendar

In a nutshell, Win32 NLS APIs give your application full control over the way a date can be represented by letting you select a given calendar type and a given formatting type for that calendar.
In fact, NLS APIs give you more flexibility than you would ever need.
As stated earlier, GetDateFormat is probably enough to format dates in a way that's locale-aware.
