---
title: Address Format
description: One of the most nonstandard formatted items you'll need to deal with in globalization is address formats.
ms.assetid: d02aec53-1433-4a43-8e20-73d9886c7a5c
ms.date: 01/24/2017
---
# Address Format

One of the most nonstandard formatted items you'll need to deal with in globalization is address formats. Thus input fields and the routines that process address information should be able to handle various formats. For instance, a very common mistake (such as in Web forms) is to insist that the user enter something in a field labeled State (or Province for Canadians). While this makes sense to people located in the United States and Canada, it confuses those from other parts of the world, since most don't have a "State" in their addresses.

You must also be flexible when performing validity checks of the data entered by the user. For example, don't assume that the ZIP code (or postal code, as it is referred to in many countries outside the United States) has any particular format or length, or that it comprises only digits. For instance, Canadian postal codes consist of two groups of three characters, such as "M5R 3H5"; a French postal code is a five-digit number, as in 92300. In some places, people might add a country or region code in front of the postal code (for example, F-92300)

The current implementation of NLS APIs and the .NET Framework do not provide any address formatting information. The best approach is to:

-   Divide the address into multiple fields for street number, building number, city, country/region, and postal code. (Note that some places—such as Taiwan—are considerred as regions by some nations and countries by others.)
-   Don't expect that all predefined fields should contain a value (such as the previous example of postal codes).
-   Be flexible for additional data that you might not usually expect in an address (such as a description of how to get there).


