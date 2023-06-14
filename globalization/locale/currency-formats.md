---
title: Currency formats
description: Display currency values using applicable conventions for the locale.
ms.date: 06/13/2023
---

# Currency formats

Like number formats, each country/region has its own standards and conventions for representing currency values. Libraries like ICU, frameworks like .NET, and programming languages like Java give you control over displaying currency values. These frameworks allow you to display currency values using the user’s locale, the locale of the currency, or any other locale.

## Currency codes and symbols

When displaying a currency, you can typically control whether to display an [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code or a currency symbol. The ISO 4217 currency code is typically the ISO 3166 country code followed by a letter corresponding to the currency name. Many countries/regions use the same currency symbol and currency name, so when the symbol might be ambiguous, a combination of country code and symbol can be used. For example,

- ISO 4217 currency code: USD
- Currency symbol: $
- Currency symbol (specific): US$

The currency symbol or code might appear before or after the value, and a space character might separate the value from the symbol or code.

## Negative amounts

Negative amounts are usually represented using a minus sign as a prefix or suffix, or by enclosing the amount in parentheses (accounting/bookkeeping). The minus sign might appear before or after the value or currency symbol, and the currency symbol might appear inside or outside the parentheses when using an accounting format.

## Number formatting and exceptions

Typically, the format of the value of the currency matches the decimal separation, grouping size, and grouping symbol of any numeric value for that locale. Switzerland is an exception, where the dot is used as a decimal separator for currency values, but a comma is typically used for any other values.

## Different currencies

You might need to format currency values for a different currency than the current locale. In this case, you need to ensure that the value is displayed as intended, including:

- The currency symbol or code is unambiguous; for example, you can differentiate between the Canadian Dollar and the Australian Dollar.
- The value uses the appropriate decimal separation, grouping size, and grouping symbol. It might be appropriate to use the user’s locale settings or the currency’s locale settings.
- The value uses the appropriate fractional amounts; for example, the smallest Japanese denomination is one yen, so fractional amounts are typically not shown when showing prices.

Displaying numeric values using the correct format for the currency is a separate issue from ensuring that the amount is appropriate or equivalent. You might need to apply an exchange rate before formatting a value for the currency.
