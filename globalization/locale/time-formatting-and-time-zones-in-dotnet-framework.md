---
title: Time Formatting and Time Zones in .NET Framework
description: 
ms.assetid: fa7e723a-f23a-454c-9312-519145d55e96
ms.date: 03/16/2016
---


# Time Formatting and Time Zones in .NET Framework

The easiest and most efficient way of doing time formatting in the .NET world is to take advantage of the *DateTime* structure that provides methods such as *DateTime.ToString* and *DateTime.Parse*. These methods allow you to perform culture-sensitive operations on a *DateTime object*. Use the *DateTimeFormatInfo* class to format and display a *DateTime* based on culture. *DateTimeFormatInfo* defines how DateTime values are formatted and displayed, depending on the culture. For example, using the *LongTimePattern*, the time 4 hours P.M., 36 minutes and 15 seconds is formatted as 4:36:15 PM for the "en-US" culture and 16:36:15 for the "fr-FR" culture number-formatting standards. (For more information and code samples, see the [Date Formatting](https://msdn.microsoft.com/en-US/globalization/mt662320) article.)

Methods and properties in the *DateTime* structure always use the local time zone for calculations and comparisons. You should consider this when using the *DateTime.Parse* method and the *DateTime.ParseExact* method. These methods provide overloads that allow you to convert the string representation of a date and time to a *DateTime* type. You can also choose to format a *DateTime* for a specific culture. If you do not specify a time zone in the string that you pass to these methods, they return the parsed date and time without performing a time-zone adjustment. The date and time are based on the system's time-zone setting. If you specify a time-zone offset, these methods parse the date/time string, convert it to UTC, and then convert it to the time on the local system.

Use the *DateTime.ToUniversalTime* method to convert a local *DateTime* to its UTC equivalent. To parse a date/time string and convert it to a UTC DateTime, use the *DateTimeStyles* enumeration *AdjustToUniversal* value with either the *DateTime.Parse* or *DateTime.ParseExact* method. These *DateTime* manipulations are illustrated in the following code example. This example creates a *DateTime* for the local time and then converts it to the UTC equivalent *DateTime*. Both types are converted to strings and written to the console. Notice that the strings differ by the UTC offset between the local time zone and UTC. (For more information on the UTC offset for various time zones, see the *TimeZone.GetUtcOffset* method in the Microsoft Developer Network documentation at [http://msdn2.microsoft.com](https://msdn.microsoft.com/).) These strings are converted back to *DateTime* types using the *DateTime.ParseExact* method. To capture the time-zone information stored in *utcdt*, the *AdjustToUniversal* value must be specified as a parameter to the *DateTime.ParseExact* method.

```C#
using System;
using System.Globalization;
using System.Threading;

public class TimeZoneSample
{
  public static void Main()
 {
 CultureInfo en = new CultureInfo("en-US");
 Thread.CurrentThread.CurrentCulture = en;
    // Create a DateTime object for the local time.
 DateTime dt = new DateTime(2001, 7, 13, 4, 0, 0);
    // Convert the local DateTime to the UTC time.
 DateTime utcdt = dt.ToUniversalTime();
    // Define a custom string format to display the DateTime
 // value. zzzz specifies the full time zone offset.
 String format = "MM/dd/yyyy hh:mm:sszzz";
    // Convert the local DateTime object to a string
 // using the custom format string and display.
 String str = dt.ToString(format);
 Console.WriteLine(str);
    // Convert the UTC DateTime to a string
 // using the custom format string and display.
 String utcstr = utcdt.ToString(format);
 Console.WriteLine(utcstr);
    // Convert the string back to a local DateTime object and
 // display.
 DateTime parsedBack = DateTime.ParseExact(str,format,en.DateTimeFormat);
 Console.WriteLine(parsedBack);
    // Convert the string back to a UTC DateTime object and
 // display. If you do not use the DateTime.ParseExact
 // method that takes a DateTimeStyles.AdjustToUniversal
 // value, the parsed DateTime object will not include the
 // time zone information.
    DateTime parsedBackUTC = DateTime.ParseExact (str, format, en.DateTimeFormat, DateTimeStyles.AdjustToUniversal);
 Console.WriteLine(parsedBackUTC);
 }
}
```
                

This code produces the following output:

```
07/13/2001 04:00:00-07:00 
07/13/2001 11:00:00-07:00 
7/13/2001 4:00:00 AM 
7/13/2001 11:00:00 AM 
```

Another vital point to consider when creating an application that is locale-aware is how currency is displayed. Since money is a valued commodity, it is essential that such things as the correct currency symbol as well as the appropriate decimal and thousands separator be used, for example, or the consequences could potentially be disastrous!

## Time Formatting in Web Pages

In **"Retrieving the Browser Language Setting"** in the [Use Locale Model](https://msdn.microsoft.com/en-us/globalization/mt662310) article, you saw how to retrieve the current browser locale on the client side and how to set the global locale of your context or session to this value. After the appropriate locale has been set, you can easily format the time using FormatDateTime, a locale-aware function. Suppose you have retrieved the Chinese (Taiwan) locale as the primary browser locale ("zh-TW" is the default value for this locale). The following code saves the current context locale (matching the server's user locale), sets the locale to Chinese (Taiwan), formats the date in Chinese (Taiwan) format, and restores the original locale.

```
currentLocale = GetLocale
Original = SetLocale("zh-TW")
DateData = FormatDateTime(Now(),vbLongTime)
Original = SetLocale(currentLocale)
```

And the output would be:

```
下午 04:16:08 
```

Obviously the scripting technology does not offer the same flexibility to manipulate time formats as NLS APIs do in the case of Win32 programming. However, the FormatDateTime function gives you the ability to display time in the user's cultural preferences in both short- and long-time formats.

## References

See the MSDN documentation for details about the following APIs:
[EnumTimeFormats](https://msdn.microsoft.com/en-us/library/ms776258.aspx)
[GetTimeFormat](https://msdn.microsoft.com/en-us/library/ms776299.aspx)
[GetTimeZoneInformation](https://msdn.microsoft.com/en-us/library/ms724421.aspx)
[SetTimeZoneInformation](https://msdn.microsoft.com/en-us/library/ms724944.aspx)
[DateTime Structure for .NET](https://msdn.microsoft.com/en-us/library/system.datetime(v=vs.110).aspx)


