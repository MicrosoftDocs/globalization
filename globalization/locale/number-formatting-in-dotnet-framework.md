---
title: Number Formatting in .NET Framework
description: 
ms.assetid: 81bc7141-92f0-432a-a241-eebfda454fd2
ms.date: 03/16/2016
---


# Number Formatting in .NET Framework

The *NumberFormatInfo* class defines how currency, decimal separators, and other numeric symbols are formatted and displayed based on culture. For example, the decimal number 10000.50 is formatted as 10,000.50 for the culture "en-US" and 10.000,50 for the culture "de-DE." An instance of *NumberFormatInfo* can be created for a specific cultureor the invariant culture, but not for a neutral culture. A neutral culture does not provide enough information to display the correct numeric format. Table 4-10 lists the standard format characters for each standard formatting pattern and the associated *NumberFormatInfo* property that can be set to modify this pattern.

![Format Character](/media/hubs/globalization/IC11711.jpg "Format Character") 

**Table 1:** Standard format characters for basic formatting patterns and the associated NumberFormatInfo property used to modify these patterns.

The following code example displays an integer using the *NumberFormatInfo* standard currency format ("c") for the specified *CurrentCulture*.

```C#
using System.Globalization;
public class TestClass
{
     public static void Main()
     {
     int i = 100;
     // Create a CultureInfo object for English in Belize.
     CultureInfo bz = new CultureInfo("en-BZ");
     // Display i formatted as currency for bz.
     Console.WriteLine(i.ToString("c", bz));
     // Create a CultureInfo object for English in the U.S.
     CultureInfo us = new CultureInfo("en-US");
     // Display i formatted as currency for us.
     Console.WriteLine(i.ToString("c", us));
     // Create a CultureInfo object for Danish in Denmark.
     CultureInfo dk = new CultureInfo("da-DK");
     // Display i formatted as currency for dk.
     Console.WriteLine(i.ToString("c", dk));
     }
}
```

This code produces the following output:

```
$100.00
kr100,00
```

As when dealing with numbers, formatting conventions for addresses vary widely from one country to another. There are also discrepancies in the actual terms used when representing addresses that you will need to handle.


