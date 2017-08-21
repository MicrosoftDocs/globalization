---
title: Currency Formatting in Win32
description: 
ms.assetid: ec54ea8e-7d6a-49a5-968f-347c463ad0f1
ms.date: 03/16/2016
---


# Currency Formatting in Win32

Win32 NLS APIs can help you display currency data in a way that's locale-aware. The GetCurrencyFormat function formats a number string as a currency string for a specified locale. The code sample on the following page formats a number string into the user locale's default format:

```C++
GetCurrencyFormat(LOCALE\_USER\_DEFAULT, // a predefined value for user locale
      NULL, // operation option
      TEXT("123.40"), // input number (see MSDN for accepted chars)
      NULL, // formatting specifications
      g\_szTemp, // output buffer
      MAX\_STR); // size of output buffer
```

Execution of the previous code would give the following result on English (United States) and Danish user locales, respectively.

![Currency format for English (United States) and Danish](/media/hubs/globalization/IC32596.jpg "Currency format for English (United States) and Danish") 

Figure 1 - Currency format for English (United States) and Danish.

With this approach, the number string is formatted to a locale-specific format and, more importantly, currency symbol! But suppose you want to represent $1,230.40 (U.S. dollars) to a Danish user. By using the first approach mentioned and formatting your string with current user locale settings (Danish), your string would in fact come out as kr 1.230,40. Of course, the main issue would be that you want to format your string in the Danish format, but you don't want to change your currency symbol (and in this case lose some of the value of your money in the transaction).

Another scenario would be the use of the euro. The .NET Framework and Windows set the default currency symbol to the euro for members of the eurozone. However, older versions of Windows, without any intervention, will still set the default currency symbol to the local currency for these countries or regions. To resolve the issue in the two scenarios just mentioned, you can take advantage of the lpFormat argument of GetCurrencyFormat. This argument is a pointer to a currency-formatting structure, where you can define your own formatting model and specify the currency symbol to be used following the formatting standard of a given locale. The following code sample uses the formatting for the currently selected user locale, but with the euro as the desired currency symbol. Here is how it works.

```C++
CURRENCYFMT CurFormat;
// first fill in the currencyfmt structure with user locale-specific information.
getlocaleinfo(locale\_user\_default, locale\_return\_number|locale\_idigits, &curformat.numdigits, str\_len):;
getlocaleinfo(locale\_user\_default, locale\_return\_number|locale\_ilzero, curformat.leadingzero, str\_len):;
getlocaleinfo(locale\_user\_default, locale\_sgrouping, &curformat.grouping, str\_len):;
getlocaleinfo(locale\_user\_default, locale\_sdecimal, &curformat.lpdecimalsep, str\_len):;
getlocaleinfo(locale\_user\_default, locale\_sthousand, &curformat.lpthousandsep, str\_len):;
getlocaleinfo(locale\_user\_default, locale\_return\_number|locale\_inegcurr, curformat.negativeorder, str\_len):;
getlocaleinfo(locale\_user\_default, locale\_return\_number|locale\_icurrency, curformat.positiveorder, str\_len):;
// set euro as the default currency symbol.
curformat.lpcurrencysymbol = text(:;"&gt;GetCurrencyFormat(LOCALE\_USER\_DEFAULT, // a predefined value for user locale
       0, // operation option
       TEXT("123.40"), // input number (see MSDN for legal chars)
       &CurFormat, // formatting specifications
       g\_szTemp, // output buffer
       MAX\_STR); // size of output buffer
```

By following the code, the result of a currency symbol formatting for the Danish locale (with kr as default currency symbol) would be: € 123,40


