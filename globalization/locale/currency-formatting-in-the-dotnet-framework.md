---
title: Currency Formatting in the .NET Framework
description: 
ms.assetid: 773de803-6a2b-4690-9cce-9b3e6f24529e
ms.date: 03/16/2016
---


# Currency Formatting in the .NET Framework

The .NET format strings are useful if you want to convert one of the standard .NET Framework data types to a string that represents that type in some other format. For example, if you have an integer value of 100 that you want to represent to the user as a currency value, you could easily use the ToString method and the currency-format string ("C") to produce a string of "$100.00". Computers that do not have English (United States) specified as the current culture will display whatever currency notation is used by the current culture. The original value contained in the data type is not converted, but a new string is returned that represents the resulting value. This new string cannot be used for calculation until it is converted back to a .NET base data type. The original value, however, can be calculated at any time.

In the following code example, the ToString method displays the value of 100 as a currency-formatted string in the console's output window.

```C#
int MyInt = 100;
String MyString = MyInt.ToString("C");
Console.WriteLine(MyString);
```

This code displays $100.00 to the console on computers that have English (United States) as the current culture.

The CurrencySymbol property of the RegionInfo class from the System.Globalization namespace can be used to retrieve the currency symbol associated with the country or region. Also, the ISOCurrencySymbol property of RegionInfo retrieves the three-character ISO 4217 currency symbol associated with the country or region.

The following example uses code that is similar to the previous example. It sets the current culture to "fr-FR" and displays an integer to the console formatted as currency. The user's local currency settings are used to format the currency. Next, the culture is set to "fr-FR" using the CultureInfo constructor that accepts the useUserOverride parameter set to false. The number is then formatted using the .NET Framework default settings, and the euro currency symbol is displayed.

```C#
using System;
using System.Globalization;
using System.Threading;
public class EuroSymbolSample
{
     public static void Main()
     {
          int i = 100;
          // Set the CurrentCulture to French in France.
          Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");
          // Display i formatted as default currency for the CurrentCulture.
          // On a version of Windows prior to Windows XP, where the user
          // has not changed the default currency to euro through
          // Control Panel, this will default to "F".
          Console.WriteLine(i.ToString("c"));
          // Set the CurrentCulture to French in France, using the
          // CultureInfo constructor that takes a useUserOverride parameter.
          // Set the useUserOverride value to false.
          Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR", false);
          // Display formatted as default currency for the CurrentCulture.
          // On a version of Windows prior to Windows XP, this will override
          //an incorrect default setting of "F" and display the euro symbol (i).
          Console.WriteLine(i.ToString("c"));
     }
}
```

If you execute this code in a Windows Forms application, the output appears as follows:
```
     100,00 F
     100,00
```

Although most European Union countries now use the euro, there might be situations-such as for legacy reasons-where it is necessary to display both the euro and the older currencies in an application. The following code example creates a CultureInfo object for the culture "fr-FR" where the default currency is the euro. To display the currency symbol for the local currency, you must use the NumberFormatInfo.Clone method to clone a new NumberFormatInfo object for the CultureInfo object and replace the default currency symbol with a local currency symbol.

```C#
using System;
using System.Globalization;
using System.Threading;
public class EuroLocalSample
{
     public static void Main()
     {
           // Create a CultureInfo object for French in France.
           CultureInfo FrCulture = new CultureInfo("fr-FR");
           // Set the CurrentCulture to fr-FR.
           Thread.CurrentThread.CurrentCulture = FrCulture;
           // Clone the NumberFormatInfo object and create
           // a new object for the local currency of France.
           NumberFormatInfo LocalFormat = (NumberFormatInfo)NumberFormatInfo.CurrentInfo.Clone();
           // Replace the default currency symbol with the local currency symbol.
           LocalFormat.CurrencySymbol = "F";
           int i = 100;
           // Display i formatted as the local currency.
           Console.WriteLine(i.ToString("c", LocalFormat));
           // Display i formatted as the default currency.
           Console.WriteLine(i.ToString("c", NumberFormatInfo.CurrentInfo));
     }
}
```

