---
title: Console Globalization
description: Language-specific operations of console applications can and should follow the locale settings of the system.
ms.assetid: dd9aec54-e3aa-4b12-a709-04c9166492ff
ms.date: 04/21/2017
---
# Console Globalization

Language-specific operations of console applications can and should follow the locale settings of the system. This will guarantee locale-authentic formatting of numbers, date, time, currency values, and collation (sorting) operations. Locale support is available for text-mode applications through both C run-time (CRT) and Win32. Those two mechanisms can not be used interchangeably: the settings of CRT locale have no effect on Win32 code, user locale does not define the behavior of the functions exported by C run-time libraries.

For new Windows applications, Win32 mechanisms are preferred over those in CRT with regard to world-ready code.

The limitations of console system in regards to [[complex-script]](https://msdn.microsoft.com/en-us/goglobal/bb688137 "complex-script") handling require special processing for locales where locale rules define complex-script output in dates or time values. However, you should avoid taking the easy route of hard-coding the format for your output. Under locales with limitations on the output text-mode applications can expose custom behavior, for example:

-   Always use Gregorian calendar under Hebrew User locale

-   Do not display AM/PM sign under Arabic User locale

-   Ignore digit substitution rules

CRT locale support is built around the *(\_w)setlocale(category, locale)* call, discussed in [[Encodings and Code Pages]](https://msdn.microsoft.com/en-us/goglobal/bb688114 "Encodings and Code Pages") part of this guide. A call to this function defines the results of all subsequent CRT-based locale-sensitive operations, not only the character encoding. The category argument defines scope of environment changes after *setlocale* is called.

In order to set the rules for formatting locale-sensitive data in accordance with the user locale, the following calls can be executed:

```C++
_wsetlocale (LC_COLLATE, L(".OCP") );  // sets the sort order`
_wsetlocale (LC_MONETARY, L(".OCP") ); // sets the currency formatting rules`
_wsetlocale (LC_NUMERIC, L(".OCP") );  // sets the formatting of numerals`
_wsetlocale (LC_TIME, L(".OCP") );     // defines the date/time formatting`
```

As mentioned in [[Encodings and Code Pages]](https://msdn.microsoft.com/en-us/goglobal/bb688114 "Encodings and Code Pages") document, ".OCP" and ".ACP" parameters always refer to the settings of the user locale, not the system locale. While selecting this locale for LC\_CTYPE or LC\_ALL is not a good choice, all other categories should be set to match the user locale, unless your console must be explicitly independent of the user's settings.


