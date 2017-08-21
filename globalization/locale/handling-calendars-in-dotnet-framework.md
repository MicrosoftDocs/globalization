---
title: Handling calendars in .NET Framework
description: 
ms.assetid: 52135192-e034-47d3-8c22-4f988b8ffdc8
ms.date: 03/16/2016
---


# Handling Calendars in .NET Framework

Similar to the Win32 paradigm - the .NET Framework handles dates in the Gregorian calendar by using data structures. Therefore, when you use the methods provided by the [DateTime](http://msdn2.microsoft.com/en-us/library/system.datetime.aspx) structure, you must be aware that the members such as the DateTime.Day property, the DateTime.Month property, the DateTime.Year property, and the DateTime.AddDays method are based on the Gregorian calendar. Even if you change the current calendar in your application's code or change date and time settings through the Regional And Language Options property sheet, the Gregorian calendar is still used to perform the calculations for these methods. This functionality prevents the arithmetic performed by these methods from being corrupted by a user's settings. If you want to perform culture-sensitive date and time operations based on the current calendar, you must use the [DateTimeFormatInfo.Calendar](http://msdn2.microsoft.com/en-us/library/system.globalization.datetimeformatinfo.calendar.aspx) property to call methods provided by the [Calendar](http://msdn2.microsoft.com/en-us/library/system.web.ui.webcontrols.calendar.aspx) class such as *Calendar.GetDayOfMonth*, *Calendar.GetMonth*, *Calendar.GetYear*, and *Calendar.AddDays*.

To handle native calendar types, the .NET Framework provides the Calendar class as well as the following Calendar implementations: GregorianCalendar, HebrewCalendar, HijriCalendar, JapaneseCalendar, JulianCalendar, KoreanCalendar, TaiwanCalendar, and ThaiBuddhistCalendar. Other things you can use include the CultureInfo class, which has a CultureInfo.Calendar property that specifies a culture's default calendar. The CultureInfo.OptionalCalendars property specifies the optional calendars supported by a culture.

The following code example in C\# creates CultureInfo objects for the culture "th-TH" (Thai in Thailand) and displays the default and optional calendars for each culture. The GregorianCalendar is further divided into subtypes by the GregorianCalendar.CalendarType property. In this example, each time the calendar is determined to be Gregorian, the CalendarType value is retrieved and displayed.

```C#
using System;
using System.Globalization;
public class TestClass
{
    public static void Main()
    {
        // Create a CultureInfo object for Thai in Thailand.
        CultureInfo th = new CultureInfo("th-TH");
        DisplayCalendars(th);
    }
    protected static void DisplayCalendars(CultureInfo cultureinfo)
    {
        CultureInfo ci = new CultureInfo(cultureinfo.ToString());
        // Display the default calendar for the culture.
        if (ci.Calendar is GregorianCalendar)
        {
            Console.WriteLine("\\n\\n");
            Console.WriteLine(
                "The default calendar for the {0} culture is: \\n{1}\\n\\n",
                    ci.DisplayName.ToString(), ci.Calendar.ToString() +
                " subtype " +
                ((GregorianCalendar)ci.Calendar).CalendarType.ToString());
        }
        else
        {
            Console.WriteLine("\\n\\n");
            Console.WriteLine(
                "The default calendar for the {0} culture is: \\n{1}\\n\\n",
                    ci.DisplayName.ToString(), ci.Calendar.ToString());
            // Display the optional calendars for the culture.
            Console.WriteLine(
                "The optional calendars for the {0} culture are: ",
                    ci.DisplayName.ToString());
            for (int i = ci.OptionalCalendars.GetLowerBound(0); i &lt;= ci.OptionalCalendars.GetUpperBound(0); i++)
            {
                if (ci.OptionalCalendars\[i\] is GregorianCalendar)
                {
                    // Display the calendar subtype.
                    String CalStr = (ci.OptionalCalendars\[i\].ToString() +
                    " subtype " +
                    ((GregorianCalendar)ci.OptionalCalendars\[i\]).CalendarType.ToString());
                    Console.WriteLine(CalStr);
                }
                else
                    Console.WriteLine(ci.OptionalCalendars\[i\].ToString());
            }
        }
    }
}
```

This code produces the following output: 

```The default calendar for the Thai (Thailand) culture is:
System.Globalization.ThaiBuddhistCalendar

The optional calendars for the Thai (Thailand) culture are:
System.Globalization.ThaiBuddhistCalendar
System.Globalization.GregorianCalendar
subtype Localized
```
As you can see, the .NET Framework offers a UI that's extensive, yet flexible and easy to use for date and calendar formatting. 


