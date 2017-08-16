---
title: User Locale
description: User locale determines which default settings a user wants for formatting dates, times, currency, and large numbers.
ms.assetid: 4c71c47c-033c-452f-9061-45609f590c19
ms.date: 02/23/2017
---


# User Locale

The user locale determines which default settings a user wants for formatting dates, times, currency, and large numbers. Although it's presented as a language (some in a combination with a country), it's not a language setting. That is, choosing the Hebrew user locale means that the user wants to adhere to the standards of Israel, not really of the Hebrew language. To avoid any confusion with this naming, the .NET Framework calls the user locale "culture information."

As its name implies, the user locale (known in Windows XP as "Standards and formats") is a variable that each individual user can set. This can be done on the fly by selecting changes from the Regional Options tab in the Regional And Language Options property sheet. (See Figure 3) Locale-aware applications should use this value to display formatted data.

When changes are made, all locale-aware applications should monitor the window message WM\_SETTINGCHANGE and should be able to update their displayed data accordingly. Numbers, currency, date, and time are some of the variables that are affected by the user-locale setting. The user locale is a user variable that cannot be changed programmatically. The only way to change it is for the user to do so manually.


