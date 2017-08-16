---
title: Do Not Compound Several Variables
description: 
ms.assetid: 3fe50767-ebe0-4411-afff-d07f7490bed4
ms.date: 06/28/2016
---
# Do Not Compound Several Variables

As stated before, there are times that variables are necessary because you might not know what needs to go in the string until run time. Things like dates, time, temperature, and number of sales are just a few examples of these types of variables. Besides giving these variables unique names, you need to make sure that you don't compound several variables together. For example, a translator ran across the following during a localization job:

```C++
"%d:%d%s on %s, %s %d, %d"
```

Needless to say, the translator did not know how to translate the word "on," since it was ambiguous what the word meant or referred to in this particular context. Once the programmer was contacted, the localizer learned what the variables stood for:

-   First %d—Hour in 12-hour format (01-12)
-   Second %d—Minute, as decimal number (00-59)
-   First %s—Current locale's A.M./P.M. indicator for 12-hour clock
-   Second %s—Full name for the day of the week
-   Third %s—Full name for the month
-   Third %d—Day of month, as decimal number (01-31)
-   Fourth %d—Year with century, as decimal number

To avoid confusion, the programmer should have used unique names. Even better, the programmer should have stored the data in language-neutral data variables-such as a time structure-and then used one of the Windows globalization services-such as National Language Support (NLS) or .NET. (For more information on these globalization services, see " [Locale Model](https://msdn.microsoft.com/globalization/mt662310)." ) Remember that even though you use unique variable names, you still need to leave enough information so the translators know what you are trying to say. 


