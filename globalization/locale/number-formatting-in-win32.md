---
title: Number Formatting in Win32
description: 
ms.assetid: c71a439f-8f5a-4ddf-a754-cae3fa9127fa
ms.date: 03/16/2016
---


# Number Formatting in Win32

The easiest way to format numbers in a way that's locale-aware is to use the GetNumberFormat API. This API customizes the format of a number string for a specified locale. The following shows how the GetNumberFormat API is used to format a given number string for the current user locale (using the default settings for number formatting that the user has defined):

```C++
GetNumberFormat(LOCALE\_USER\_DEFAULT, // locale (current user locale)
          0,                           // options
          TEXT("1234567890.12345"),    // input string (see MSDN for legal chars)
          NULL,                        // formatting information
          g\_szTemp,                   // formatted string buffer
          MAX\_STR);                   // size of buffer
```

For more advanced number formatting in the Win32 programming model, the GetLocaleInfo API can be used to retrieve most of the number-formatting parameters (such as thousands separators, decimal separators, and negative numbers). Here are the appropriate flags to use as LCType in your calls to GetLocaleInfo, in order to retrieve each one of the number-formatting parameters.

-   Thousands separator. LCType flag set to LOCALE\_STHOUSAND
-   Decimal separator. LCType flag set to LOCALE\_SDECIMAL
-   Negative numbers. LCType flag set to LOCALE\_INEGNUMBER

Possible return values are shown in Table 1 below.

![Number Formatting](/media/hubs/globalization/IC109839.jpg "Number Formatting") 

**Table 1:** Return values of various LCType flags.

**Native digits.** LCType flag set to LOCALE\_SNATIVEDIGITS. Here is a code sample that deals with native digits:

```C++
GetLocaleInfo(LOCALE\_USER\_DEFAULT, // LCID (current user locale)
          LOCALE\_SNATIVEDIGITS,     // information type (native digits)
          &g\_szTemp,                // returned value
          sizeof (g\_szTemp));       // size of buffer
```

This code would produce the following result on English (US) and Farsi locales, respectively:

![Native Digit](/media/hubs/globalization/IC124322.jpg "Native Digit") 

**Figure 1:** Native digits for English (US) and Farsi.

**Digit Substitution.** Digit substitution defines which set of digits (with its associated shapes) should be used for presenting numbers. This information can be retrieved with the LCType flag set to LOCALE\_IDIGITSUBSTITUTION. The table below shows the possible return values:

![Digit Substitution](/media/hubs/globalization/IC35857.jpg "Digit Substitution") 

**Table 2:** Return values of LOCALE\_IDIGITSUBSTITUTION


