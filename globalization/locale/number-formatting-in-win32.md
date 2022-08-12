---
title: Number Formatting in Win32
description: The easiest way to format numbers in a way that's locale-aware is to use the GetNumberFormat API.
ms.assetid: c71a439f-8f5a-4ddf-a754-cae3fa9127fa
ms.date: 03/16/2016
ms.topic: reference
author: pallep
---

# Number Formatting in Win32

> [!NOTE]
> Examples in this topic use LCID to identify locales.
> Microsoft has been migrating toward the use of locale names instead of locale identifiers since Windows Vista.
> Any application that runs only on Windows Vista and later should use the ...Ex versions of most NLS APIs,
> which use a locale name to identify a locale instead of an LCID.
> See [Locale names and LCID deprecation](locale-names.md) for more information.

The easiest way to format numbers in a way that's locale-aware is to use the GetNumberFormat API.
This API customizes the format of a number string for a specified locale.
The following shows how the GetNumberFormat API is used to format a given number string for the current user locale (using the default settings for number formatting that the user has defined):

```cpp
GetNumberFormat(LOCALE_USER_DEFAULT, // locale (current user locale)
          0,                           // options
          TEXT("1234567890.12345"),    // input string (see MSDN for legal chars)
          NULL,                        // formatting information
          g_szTemp,                   // formatted string buffer
          MAX_STR);                   // size of buffer
```

For more advanced number formatting in the Win32 programming model, the GetLocaleInfo API can be used to retrieve most of the number-formatting parameters (such as thousands separators, decimal separators, and negative numbers).
Here are the appropriate flags to use as LCType in your calls to GetLocaleInfo, in order to retrieve each one of the number-formatting parameters.

- Thousands separator. LCType flag set to LOCALE_STHOUSAND
- Decimal separator. LCType flag set to LOCALE_SDECIMAL
- Negative numbers. LCType flag set to LOCALE_INEGNUMBER

Possible return values are shown in Table 1 below.

| Value | Format (meaning) |
| --- | --- |
| 0 | Left parenthesis, number, right parenthesis. Example: (1.1) |
| 1 | Negative sign, number. Example: -1.1 |
| 2 | Negative sign, space, number. Example: - 1.1 |
| 3 | Number, negative sign. Example: 1.1- |
| 4 | Number, space, negative sign. Example: 1.1 - |

**Table 1:** Return values of various LCType flags

## Native digits

To use native digits the LCType flag set to LOCALE_SNATIVEDIGITS.
Here is a code sample that deals with native digits:

```cpp
GetLocaleInfo(LOCALE_USER_DEFAULT, // LCID (current user locale)
          LOCALE_SNATIVEDIGITS,     // information type (native digits)
          &g_szTemp,                // returned value
          sizeof (g_szTemp));       // size of buffer
```

This code would produce the following result on English (US) and Persian locales, respectively:

![Native Digit](/globalization/locale/images/Native_Digits.jpg "Native Digit")

**Figure 1:** Native digits for English (US) and Persian

## Digit Substitution

Digit substitution defines which set of digits (with its associated shapes) should be used for presenting numbers.
This information can be retrieved with the LCType flag set to LOCALE_IDIGITSUBSTITUTION.

The table below shows the possible return values:

| Value | Meaning |
| --- | --- |
| 0 | Content - The shape depends on the previous text in the same output. |
| 1 | None/Arabic - Gives full Unicode compatibility. |
| 2 | Native - National shapes determined by LOCALE_SNATIVEDIGITS. |

**Table 2:** Return values of LOCALE_IDIGITSUBSTITUTION
