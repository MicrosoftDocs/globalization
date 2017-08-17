---
title: Security Guidelines for International
description: 
ms.assetid: 00ad82fb-42ba-4df8-b78f-962b98d5cc97
ms.date: 11/16/2016
---

# Security Guidelines for International

Most software products have international versions that are part of multi-national networks around the world. Having one vulnerable computer on a corporate network, whether it is an English version or an international version, threatens the whole corporate security.

***NOTICE*** *: This article is not a complete security threat model for international software. You must develop specific threat models and follow the necessary security precautions including design review, code review, and functional testing to meet the security requirements. International software threat models will vary depending on the technologies and methods used.*

Basic software security requirements include protecting software against:

- Crashes (denial of service)
- Misbehavior (information disclosure and elevation of privileges)

The [Security Developer Center](http://msdn2.microsoft.com/security/) explains these concepts in detail. This article presents some of the commonly known problems found in international software products and raises awareness of potential problems that may impact security when globalizing and localizing software products.

## A Defensive Strategy

Both development and localization teams are responsible for securing international software to ensure that software companies deliver trustworthy products; here is how they are involved:

**Developers** must pay special attention to software resources as a potential threat to their software applications, and they should use defense in depth techniques.

Software defense in depth means writing source code that is suitable for both globalization and localizability areas. Developers must simplify the use of string resources that are to be used only for display. Such simplification will avoid many problems and will increase the software product’s robustness.

**Localization teams** modify software resources to make the product suitable for local markets. By including poorly localized resources, localization vendors may introduce security threats into products. The application may crash if the string resources do not adhere to certain guidelines. Localization teams should use resource commenting and localization verification procedures to deliver high-quality localized resources.

Improving localization quality means validating the localized string resources based on predefined instructions and ensuring that the localized resources meet high localization standards.

## Types of Issues

The guidelines below are provided to help the developer and tester through potential security issues that are particular to the international space. These guidelines are not exhaustive, but are a record of our experience.

| **Category** | **Issue** | **Description** |
|--------------|-----------|-----------------|
| **Buffer Overrun Exploits** | Buffer size mismatches when converting between UTF-8 and UTF-16. | Occurs when you are working with UTF-8 and UTF-16 buffers. |
| | Buffer size mismatches when converting between MBCS and WideChar (UTF-16) | Occurs when the length of a string in bytes is confused with the length in characters. |
| | Length miscalculation when processing surrogate pairs | How is high surrogate at the end of the buffer handled? Will the developer look past the end of the buffer? |
| | Locale Specific Buffer Overruns | Setting the locale so that formatted numeric or date strings causes a buffer overflow. <br />Example: Code assumes short (e.g., US) date type, but receives long type (e.g., Japanese) therefore causing buffer overrun. |
| | Buffer Overruns caused by Localization | Example: While loading localized strings, the program allocates an internal static buffer of size 1024. By the time it has loaded the 22 ^nd^ string from the string table the length of the buffer has gone to 0 and there is a table-overrun. |
|**Regular Expressions** | **Patterns** need to be designed with international text in mind | Understand whether international text is valid in your design. [http://www.unicode.org/unicode/reports/tr18/](http://www.unicode.org/unicode/reports/tr18/) <br />Example: Incorrect RegEx handling may result in inappropriate denial or granting of access during validation of non-ASCII input (e.g., text, symbols, non-Latin digits classes such as Bengali and Thai) |
| | Understand how your Regular Expressions **engine** does or does not support international text. | Craft the pattern knowing the capabilities of your engine. [http://www.unicode.org/unicode/reports/tr18/](http://www.unicode.org/unicode/reports/tr18/) <br />Example: Unassigned ranges either pass or fail regular expression query search. If, for example, security verification checks to validate if the given character is in a specific range, it might consider unassigned range characters as permissible by default. This is a potential security threat. <br />Incorrect RegEx handling may require administrators to lower the level of security (when the default settings cause denial of non-Latin text) or may accept unwanted characters (for example, classifying non-standard digits—Bengali, Thai—as acceptable digits). |
| | LCIDs | Any component that require passing the LCID back and forth between the client and the server—modifying the LCID maliciously in the middle of these operations may expose data on the server that is either corrupt on inappropriate. |
| **Canonicalization Issues** | General | The string undergoes one of the following transformations after validation, and thus what was confirmed as safe during the validation stage is not the same string that gets used. <br />The developer must be on the lookout for this kind of transformations after the validation stage has taken place. For example, from escaped UTF-8 to unescaped UTF-8. |
| | Overlong UTF-8 | Primitive UTF-8 decoders fail to detect Unicode characters encoded multiple times. |
| | Best Fit | Characters not represented in the target character set may be replaced with a “best fit” character instead of the default character (e.g., fraction slash can become a normal slash). |
| | Normalization | Normalization is a converting a string segment to a unique, equivalent form. <br />Example: Normalizing composite character sequences into pre-composed characters (i.e., a + \` to à).<br />More Information: [http://www.unicode.org/unicode/reports/tr15/](http://www.unicode.org/unicode/reports/tr15/) |
| | Homograph Attacks | Unicode equivalents from outside of ANSI script can be used to trick the user into going to a different site/server etc. This becomes a larger issue with introduction of IDN - International Domain names. The basic example is writing [http://www.microsoft.com/](https://www.microsoft.com/) with a Cyrillic “o” or a “0” zero.<br />[https://en.wikipedia.org/wiki/IDN_homograph_attack](https://en.wikipedia.org/wiki/IDN_homograph_attack) |
| **Date Verification** | Use of formatted date for verification can fail with certain Locales. | Algorithm that verifies expiration dates and time span lengths can be broken by changing the language settings when the algorithm uses a formatted date. These problems are commonly seen on the Web. <br />May not be an issue with a certificate-based security model because they verify against the DATE data type. |
| **Risky APIs** | Dangerous APIs that are very common | An internet search will reveal the most recently document risky APIs. |
| **Government Requirements** | | Local governments may have their own specific requirements, such as the French Encryption Declaration, you must be aware of these regulations. |


