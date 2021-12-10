---
title: Date formatting
description: Each date displays the day, month, and year, but the presentation order and separators can vary in different countries/regions.
ms.assetid: 05632b68-e221-4d77-a85b-68f9d3781ecf
ms.date: 01/24/2017
---
# Date formatting

For many use cases, date formatting is not constant through out the world.
Although each date basically displays the year, month, and day, their presentation order and separators vary greatly.
In fact, there may be differences between regions within the same country.

To help illustrate this, let's look at two basic date formats:

| Date format | Example |
| -- | -- |
| Long Date | Tuesday, October 12, 1954 |
| Short Date | 10/12/54 |

Now let's compare these formats between United States, Mexico, and Japan.

## Long date

| Region | Long date |
| -- | -- |
| United States | Tuesday, October 12, 1954 |
| Mexico        | martes 12 de octubre de 1954 |
| Japan         | <span lang="ja">1954年10月12日</span> |

Obviously, the names of the months and days of the week are different from locale to locale.
However, there are other notable differences as well.
For Mexico, the day comes before the month, everything is lowercase and the article "de" has been added.
In Japan, the day of the week is not displayed, and the translations for day, month and year act more like separators.

## Short date

| Region | Short date |
| -- | -- |
| United States | 10/12/54 |
| Mexico        | 12/10/54 |
| Japan         | 54/10/12 |

In the short date, we again see that in the Mexico example the order is day/month/year as compared to the United States where it is month/day/year.
In Japan, the order is year/month/day.
This can cause confusion if not watched carefully.

For example, the ambiguous short date specified as ***07/04/01*** could mean:

| Region | Long date (US) |
| -- | -- |
| United States | July 4<sup>th</sup>, 1901 |
| Mexico        | April 7<sup>th</sup>, 2001 |
| Japan         | April 1<sup>st</sup>, 2007 |

These examples shows why you should use the date APIs when dealing with dates.
Not only will they handle the correct format, but they will also display the correct translations for the long dates, possibly saving translation costs.

## Universal date format

So far, this discussion has been purely around formatting dates for display to the user in a user interface.
Dates in storage and transmission should generally be using a locale-independent format, such as a binary representation or an application ISO 8601.
These can then be parsed to a binary date/time and reformatted using locale-aware APIs for display to the user.

For some use cases, such as a package manifest or server log, you may not know a user locale or require a readable format that is not dependent on locale or language.

While there isn't a truly universal format understood by everyone in the world, but you can achieve at least a widely understood, unambiguous, and sortable format that might be acceptable for many use cases: `yyyy-MM-dd`.

Broken down:

- `yyyy` provides an unambiguous 4-digit year.
- `mm` provides a two-digit month number.
- `dd` provides a two digit day.
- Components are separated for readability with a dash (-`).
- Ordered that dates sort properly using a basic efficient string sort.

.NET provides convenient formats for formatting a date designed for transmission (round-trip) (`"o"`), and universal/sortable format (`"U"`).
See [Standard date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings).

See also

- [Wikipedia: ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)

- [ISO 8601 - Date and time format](https://www.iso.org/iso-8601-date-and-time-format.html)

- [W3C Quality Tips: Use international date format (ISO)](https://www.w3.org/QA/Tips/iso-date)
