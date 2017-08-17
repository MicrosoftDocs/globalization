---
title: Sorting and String Comparison in .NET Framework
description: 
ms.assetid: 475f7db4-8dd8-4ba1-bab0-43132d9214b2
ms.date: 01/25/2017
---


# Sorting and String Comparison in .NET Framework

The [[CompareInfo]](http://msdn2.microsoft.com/en-us/library/system.globalization.compareinfo.aspx) class provides a set of methods you can use to perform culture-sensitive string comparisons. The [[CultureInfo.CompareInfo]](http://msdn2.microsoft.com/en-us/library/system.globalization.cultureinfo.compareinfo.aspx) property, which is an instance of the [[CultureInfo]](http://msdn2.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx) class, defines how to compare and sort strings for a specific culture. The [[String.Compare]](http://msdn2.microsoft.com/en-us/library/84787k22.aspx) method uses the information in the CultureInfo.CompareInfo property to compare strings. This method returns a negative integer if string1 is less than string2, zero (0) if string1 and string2 are equal, and a positive integer if string1 is greater than string2.


