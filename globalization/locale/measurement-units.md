---
title: Units of measurement
description: Learn about different systems of measurement and avoiding issues when converting values.
ms.date: 06/13/2023
---

# Units of measurement

The [International System of Units](https://www.bipm.org/measurement-units) (SI) is now the most widely used system of measurement. The SI defines base units that include second for time, metre (meter) for length and kilogram for mass. However, the *US customary units* (for example, inch, foot, yard, and mile for length, degrees Fahrenheit for temperature) are in common use in the USA. The comparable imperial system of units is still in common use in parallel with the SI system in several countries/regions; for example, to measure distance in the UK. There are differences between US customary units and the imperial system of units; for example, the US fluid gallon is smaller than the imperial fluid gallon.

When converting measurements between two different systems of units, it's important to ensure that you know both systems of measurement in use, especially if the unit of measurement is ambiguous. For example, a fluid ounce could be either a US fluid ounce or an imperial fluid ounce. Programming languages and frameworks don't usually provide conversions between SI/metric units and US or imperial units, or between US units and imperial units. You might be able to use a published library for these types of conversions.

Similarly, your programming language or framework might provide methods to determine whether the locale uses the SI (metric) system or another measurement system. These methods don't handle the case where the national standard is one system, but different units of measurement are used in specific cases.
