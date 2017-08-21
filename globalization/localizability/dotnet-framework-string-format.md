---
title: .NET Framework -- String.Format
description: 
ms.assetid: c1386557-8372-486b-b98e-6e84286e9255
ms.date: 06/28/2016
---
# .NET Framework—String.Format

The .NET Framework has a counterpart to Win32's FormatMessage—the String.Format method. It allows you to number your variable placeholders so that localizers can rearrange them depending on the syntax of the language into which you are translating, without having to rearrange the variables themselves in the method call. The one difference between FormatMessageand String.Format is that instead of using FormatMessage's percent sign (%) plus some number to designate the placeholder, String.Format encompasses the number within braces "{ }." So the earlier example would be changed from the FormatMessage syntax of:

```C#
"Not enough memory to %1 the file %2."
```

to the String.Format syntax of:

```C#
"Not enough memory to {0} the file {1}."
```

The call in your program would be:

```C#
String.Format("Not enough memory to {0} the file {1}", sFunc, sFile);
```

The format parameter is embedded with zero or more format specifications of the form, [{ N \[, M \]\[: formatString \]}], where:

-   N is a zero-based integer indicating the argument to be formatted.
-   M is an optional integer indicating the width of the region to contain the formatted value, padded with spaces. If the sign of M is negative, the formatted value is left-justified in the region; if the sign of M is positive, the value is right-justified.

FormatString is an optional string of formatting codes.

If the value of format is "[Brad's dog has {0,-8:G} fleas.]", [arg0] is a 16-bit integer with the value 42, (and in this example, underscores represent padding spaces) then the return value will be:

```C#
"Brad's dog has 42______ fleas."
```

The .NET Framework has also added the idea of an argument placeholder to its Console.Write method. So an application that uses the standard input, output, and error streams for console applications can use the same syntax as the String.Format method to allow it to be more localizable, such as shown here:

```C#
Console.Write("Not enough memory to {0} the file {1}", sFunc, sFile);
```


