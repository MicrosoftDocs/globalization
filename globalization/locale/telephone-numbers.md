---
title: Telephone number formats
description: Learn about telephone number formats, including country codes, area codes, and trunk prefixes, and how to format them for display.
ms.date: 06/13/2023
---

# Telephone number formats

Telephone numbers are typically assigned to consumers of landline, mobile, and satellite phones according to national telephone numbering plans. Telephone numbering plans can be either a closed numbering plan with a fixed number of digits in each telephone number, or an open numbering plan with a variable number of digits.

The [E.164 standard](https://www.itu.int/rec/T-REC-E.164), published by the International Telecommunication Union as “The international public telecommunication numbering plan” is an open numbering plan that defines the format for international telephone numbers. The standard requires that a telephone number has a maximum of 15 digits, separated as the first one to three digits as a country code and the remaining digits corresponding to the subscriber’s telephone number.

The [North American Numbering Plan](https://nationalnanpa.com/) (NANP), used for telephone numbers in countries/regions such as United States, Canada, and Jamaica, is a closed numbering plan. All countries/regions in the NANP have a country code of 1. The subscriber number is 10 digits, with the first three digits being an area code that corresponds to a country or a regional service area. When calling a number within the area code, it might be possible to omit the area code. Being able to omit the area code is becoming less common, especially in the United States.

A trunk prefix is one or more digits that must be entered prior to entering a subscriber’s telephone number. An international call prefix is an example of a trunk prefix that allows you to enter a country code when calling a subscriber in another country/region. Common international call prefixes are 011 (used within the NANP) or 00 (recommended by the International Telecommunication Union). As the international call prefix varies by country/region, the plus (+) sign is used to represent the international call prefix. Many mobile phones allow the plus (+) sign to be used instead of entering the appropriate international call prefix. Calling a domestic number might also require a trunk prefix, typically 0. The domestic trunk prefix is often omitted when a call originates from a different country/region.

When displaying a subscriber’s telephone number in the United States, several formats are common:

- (XXX) XXX-XXXX
- XXX-XXX-XXXX
- +1 XXX-XXX-XXXX

As all countries/regions in the NANP have 10 digits, the 3+3+4 grouping can be used consistently for telephone numbers in the NANP. This isn't true of numbering plans in other countries and regions. Subscriber numbers might be different lengths and different groupings, from two to six digits, are used. Similarly, different separators, including hyphens, periods, and spaces might be used to separate groups of digits. Parentheses might be used for optional area codes or trunk prefixes.

Telephone service providers can support telephone numbers where the subscriber, not the caller, pays for the cost. These telephone numbers are called toll-free or freephone telephone numbers. Depending on the provider, these telephone numbers might be limited to domestic customers. To support international users, a Universal International Freephone Number (UIFN) service might be required.

Businesses frequently use private branch exchanges. When calling a user of a private branch exchange, a telephone extension number can be used to route the call. The extension information isn't part of the E.164 standard and might be displayed after the telephone number, prefixed with the letter “x” or the word “extension”.

When designing a form for users to enter telephone numbers, the best practice is to display a dropdown list of country codes, and a text field for the subscriber number. If you plan to validate the subscriber number, ensure that you're validating the format against appropriate formats for that country/region, not only the NANP 10-digit format. Alternatively, you could normalize the subscriber number before storing it. You might also need to handle any extension number that is part of the data that is entered as part of the subscriber number.

For displaying telephone numbers, you should consider whether you should show the number formatted as an international number (+ followed by country code) or a domestic number with the appropriate trunk prefix. To help to format telephone numbers, Windows UWP provides [Windows.Globalization.PhoneNumberFormatting](/uwp/api/windows.globalization.phonenumberformatting) and libraries like Google’s [libphonenumber](https://github.com/google/libphonenumber) provides support for Java, JavaScript, and C++.
