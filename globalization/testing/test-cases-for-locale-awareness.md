---
title: Test cases for locale awareness
description: Globalization test cases for verifying the data in various regional settings.
---

# Test cases for locale awareness

In general, applications should provide default options that reflect the user's locale, and allow the user to override defaults.

## Locale-independent data persistence

Applications must store and retrieve documents containing locale-sensitive data (such as the date, time, and numeric information).
Check that this data is stored in a universal, locale-neutral form.
This data is then formatted for display and follows the user's locale.

**Applicability**: All applications that store data in an external persistent storage.

## Adherence to locale standards

Verify that data can be entered, interpreted, stored, and retrieved in a manner consistent with the user's locale.
Examples of locale-specific data are date, time, currency, and numbers.

Currency values should be stored with the unit of currency, and formatted with the corresponding currency symbol for display.

**Applicability**: All applications

## Dynamic usage of format separators

Verify that date, time, and numeric values are parsed using locale-aware methods.
Make sure the separators or "picture" "formats are derived from locale data or localized data in the application.

**Applicability**: Applications that allow you to enter formatted data.

## Paper and envelope sizes

For information that is going to be printed, check the appropriate default paper and envelope sizes are based on the user's locale.
Give the user the ability to choose paper size and orientation.
Verify that the application relays this information to the printing device.

**Applicability**: Applications that format printable information.

## Measurement-system independence

Verify that physical dimensions use the measurement system corresponding to the user's locale by default.
The measurement system is usually a choice between the Metric system or the U.S. Customary System.
A good application will also allow the user to override the default units with a choice of units or measurement system.

The unit of measurement should be stored with the data.
Or, an application may store data normalized to a fixed measure, then convert and format the value for display and input.

**Applicability**: Applications that use real physical dimensions.
