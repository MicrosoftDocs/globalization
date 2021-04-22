---
title: Currency Formatting
description: Currency symbol, Currency symbol placement, and Negative-amount display can vary in different countries/regions.
ms.assetid: 
ms.date: 
---

http://cldr.unicode.org/translation/numbers-currency/number-patterns

USD vs $ etc.
Accounting (negative numbers in parenteses) 

Best practices for formatting currencies for locales other than the current locale - i.e. displaying USD values when you are in fr-FR.









# Currency Formatting

Currency formatting needs to take into consideration these following elements:

-   **Currency symbol** — This can be a pre-defined symbol such as the European Euro '€' or a combination of letters like the use of 'GBP' for British Pound.
-   **Currency symbol placement** — It can be either place before or after the digits.
-   **Negative-amount display** — Several of the ways to display negative amounts are:
 

|**Description**                                                       |**Country**   |**Formatting**|
|---|---|---|
|The negative sign before both the currency symbol and number.         |UK            |-£127.54|
|                                                                      |France        |-127,54 €|
|The negative sign before the number but behind the currency symbol.   |Denmark       |kr-127,54|
|The negative sign after the number.                                   |Netherlands   |€ 127,54-|
|The use of parentheses.                                               |US            |(\$127.54)|

Most currencies use the same decimal and thousands separator that the numbers in the locale use, but this is not always true. In some places in Switzerland, they use the period as a decimal separator for Swiss frans (Sfr. 127.54), but then use commas as the decimal separator everywhere else (127,54).

![Currency format](https://docs.microsoft.com/globalization/locale/images/Chinese_Currency.jpg "Currency format") 

**Figure 1.** Currency format in Region settings

### See more info in the below links:

 - [Currency Formatting in Win32](currency-formatting-in-win32.md)
 - [Currency Formatting in .NET Framework](currency-formatting-in-the-dotnet-framework.md)


