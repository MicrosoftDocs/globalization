---
title: Number formats
description: Discover differences in number formats by country/region, including decimal separators, grouping, and symbols.
ms.date: 06/13/2023
---

# Number formats

Every country/region has its own standards and conventions for representing numbers. Differences include the character used for the decimal separator, how negative numbers are represented, and how currencies are displayed. Fortunately, libraries like ICU, frameworks like .NET, and programming languages like Java help you display and parse numbers in the correct format for users’ locales.

This topic will discuss some of the differences in number formats by country/region.

##Decimal separation

The decimal separator is a character that splits the representation of a number into the integer and the fraction. Two characters frequently used for the decimal separator are the comma (, U+002C) and the dot (. U+002E), also known as the full stop, period, or decimal point. Other characters include the Arabic decimal separator (٫ U+066B), the apostrophe (' U+0027), and the middle dot (· U+00B7).

The decimal separator can depend on context. For example, in Switzerland, the comma is used as the decimal separator for most situations, but the dot is used for currencies.

## Number grouping and separation

To make it easier to read large numbers, grouping can be used for both the integer and fractional part of the number. European languages often use groups of 3 digits based on the 10^3 names of higher power numbers, whereas China, Japan, and Korea commonly use groups of 4 digits based on the 10^4 names.

The South Asian grouping system used in countries like India starts grouping at 4 digits, then then every second power of 10. For example, 10^7 is represented as 1,00,000.

Digit grouping rules can specify when grouping should occur. In Germany, the DIN 1333 standard specifies that a space should be used as a separator starting at 5 digits, so 1234 but 12 345. Note that the standard might differ from normal use, which for Germany is using the comma as the grouping separator (12,345).

Like decimal separation, various characters can be used as the grouping separator, including space (U+0020), comma (, U+002C), and dot (. U+002E). The separator used can also depend on context. For example, in the United States, the comma is typically used for the grouping separator; however various publication standards follow international standards in using either a space or a thin space character.

## Negative and positive numbers

Negative numbers are typically represented with a prefix of a hyphen-minus character (U+002D). The plus sign character (U+002B) can be used as a prefix for positive numbers. Other formats are also common, including the use of parentheses (U+0028 and U+0029) to represent negative numbers in accounting formats.

## Other symbols

In addition to the decimal separator, the grouping separator, and the minus sign, other symbols are frequently used when formatting numbers. These include symbols to represent a percentage, a per mille (parts per thousand) amount, a currency, an approximate value, an exponent, or an approximate value.

Convention or standards might specify the order of the numeric value and the symbols and spaces between symbols and numeric values. For example, a price might be represented as € -1.234,56 in the Netherlands and as -1 234,56 € in France. For more information about currency formatting, see [Currency formats](currency-formats.md).

## Using locales and libraries, frameworks, and programming languages to format numbers

Localization frameworks and libraries can help you display numbers in the correct format for the user’s locale. Both .NET and ICU provide locale-aware number formatting with defaults for various styles, including currencies, exponents (scientific notation).

While the default behavior for libraries, frameworks, and programming languages for formatting numbers might be sufficient, the frameworks do allow the developer full control when formatting numbers. Some examples of formatting numbers beyond using just digits and symbols include:

- numbers in words: “one-thousand, two hundred and thirty-four”
- ordinal numbers: “1st” or “twenty-third”
- compact forms of numbers: “123K” instead of 123,000

Your framework might support these behaviors by default or might provide a rules-based formatter that allows you to extend the behavior that you need.
