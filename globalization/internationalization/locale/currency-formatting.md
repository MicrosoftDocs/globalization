This documentation is archived and is not being maintained.

# Currency Formatting

Currency formatting needs to take into consideration these following elements:

-   **Currency symbol** -- This can be a pre-defined symbol like the European Euro '€' or a combination of letters like the use of 'GBP' for British Pound.
-   **Currency symbol placement** -- It can be either place before or after the digits.
-   **Negative-amount display** -- Several of the ways to display negative amounts are:
      --------------------------------------------------------------------- ------------- ----------------
      **Description**                                                       **Country**   **Formatting**

      The negative sign before both the currency symbol and number.         UK            -£127.54
                                                                            France        -127,54 F

      The negative sign before the number but behind the currency symbol.   Denmark       kr-127,54

      The negative sign after the number.                                   Netherlands   € 127,54-

      The use of parentheses.                                               US            (\$127.54)
      --------------------------------------------------------------------- ------------- ----------------

Most currencies use the same decimal and thousands separator that the numbers in the locale use, but this is not always true. In some places in Switzerland, they use the period as a decimal separator for Swiss frans (Sfr. 127.54), but then use commas as the decimal separator everywhere else (127,54).

![Currency format](https://i-msdn.sec.s-msft.com/dynimg/IC848905.jpg "Currency format") 

**Figure 1.** Currency format in Region settings

### See more info in the below links:

[](https://msdn.microsoft.com/en-us/library/mt691866)
## Currency Formatting in Win32

[](https://msdn.microsoft.com/en-us/library/mt691867)
## Currency Formatting in .NET Framework

[Show:]{} Inherited Protected
