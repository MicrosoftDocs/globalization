---
title: Sorting and String Comparison in Win32
description: 
ms.assetid: 3de45dab-a908-4c80-8915-10d8a0abc625
ms.date: 01/25/2017
---


# Sorting and String Comparison in Win32

The [[lstrcmp]](http://msdn2.microsoft.com/en-us/library/ms647488.aspx) and [[lstrcmpi]](http://msdn2.microsoft.com/en-us/library/ms647489.aspx) Win32 functions compare two character strings in a case-sensitive or case-insensitive manner, respectively, following the sorting rules and standards that are defined for the currently selected user locale. The lstrcmp and lstrcmpi functions compare two strings by checking the first characters against each other, the second characters against each other, and so on until they find an inequality or reach the ends of the strings. These functions return the difference of the values of the first unequal characters they encounter. For example, lstrcmp determines that "abcz" is greater than "abcdefg" and returns the difference of the code-point numbers that correspond to "z" and "d." The selected user locale determines which string is greater (or whether the strings are the same).


