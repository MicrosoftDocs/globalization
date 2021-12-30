---
title: Security guidelines for international
description: This article presents security guidelines for globalization.
ms.assetid: 00ad82fb-42ba-4df8-b78f-962b98d5cc97
ms.date: 11/16/2016
---

# Security guidelines for international

Most software products have international versions that are part of multi-national networks around the world.
Having one vulnerable computer on a corporate network, whether an English version or an international version, threatens the whole corporate security.

> [!IMPORTANT]
> This article is not a complete security threat model for international software.
You must develop specific threat models and follow the necessary security precautions including design review, code review, and functional testing to meet the security requirements.
> International software threat models will vary depending on the technologies and methods used.

Basic software security requirements include protecting software against:

- Crashes (denial of service)
- Misbehavior (information disclosure and elevation of privileges)

This article presents some of the commonly known problems that may impact security when globalizing and localizing software products.

See [Microsoft Security Engineering](https://www.microsoft.com/securityengineering) to discover the security engineering practices used at Microsoft to build and operate highly secure applications and services.

## A defensive strategy

Development and localization teams are both responsible for securing international software.
Each team has specific responsibilities to ensure trustworthy products.

**Developers** must pay special attention to software resources as a potential threat to their software applications, and they should use defense-in-depth techniques.

Software defense in depth means writing source code that is suitable for both globalization and localizability areas.
Developers must simplify the use of string resources that are to be used only for display.
Such simplification will avoid many problems and will increase the software product’s robustness.

**Localization teams** modify software resources to make the product suitable for local markets.
By including poorly localized resources, localization vendors may introduce security threats into products.
The application may crash if the string resources do not adhere to certain guidelines.
Development and localization teams should use resource commenting and localization verification to deliver high-quality localized resources.

Improving localization quality means validating the localized string resources based on predefined instructions and ensuring that the localized resources meet high localization standards.

## Types of issues

The guidelines below help the developer and tester through potential security issues in international software.
These guidelines are not exhaustive, but are a record of real-world experience.

| **Category** | **Issue** | **Description** |
|--------------|-----------|-----------------|
| **Buffer overrun exploits** | Buffer size mismatches when converting between UTF-8 and UTF-16. | Occurs when working with UTF-8 and UTF-16 buffers. |
| | Buffer size mismatches when converting between MBCS and WideChar (UTF-16) | Occurs when the storage requirement for a string in bytes is confused with the length in characters. |
| | Length miscalculation when processing surrogate pairs | How is high surrogate at the end of the buffer handled? Will the developer look past the end of the buffer? |
| | Locale-specific buffer overruns | Setting the locale so that formatted numbers or dates causes a buffer overflow. <br />Example: Code assumes short date type, but receives a long type causing a buffer overrun. |
| | Buffer overruns caused by localization | Example: While loading localized strings, the program allocates an internal static buffer of size 1024 bytes. By the time it has loaded the 22^nd^ string from the string table, the available buffer has gone to 0 and there is a buffer overrun. |
|**Regular Expressions** | Patterns must be defined with international text in mind | Understand whether international text is valid in your design. [Unicode technical report TR18](http://www.unicode.org/unicode/reports/tr18/) <br />Example: Incorrect RegEx handling may result in inappropriate denial or granting of access during validation of non-ASCII input. For example, text, symbols, and non-Latin digits such as in Bengali and Thai. |
| | Understand how your regular expression engine does or does not support international text. | Craft the pattern knowing the capabilities of your engine. [Unicode technical report TR18](http://www.unicode.org/unicode/reports/tr18/) <br />Example: Unassigned ranges either pass or fail regular expression query search. If security verification checks to validate if the given character is in a specific range, it might consider unassigned range characters as permissible by default. This is a potential security threat. <br />Incorrect RegEx handling may require administrators to lower the level of security when the default settings cause denial of non-Latin text. A bad RegEx may accept unwanted characters; for example, classifying non-standard digits in Bengali and Thai as acceptable digits. |
| | Locale IDs | Any component that requires passing the LCID or other locale identifier between the client and the server may expose the identifier to malicious man-in-the-middle attacks. Altering the ID may expose data on the server that is corrupt or inappropriate. |
| **Canonicalization issues** | General | The string is transformed after validation. What was confirmed as safe during the validation stage is not the same string that gets used. <br />The developer must be on the lookout for this kind of transformation after the validation stage. For example, the transformation from escaped to unescaped text. |
| | Overlong UTF-8 | Primitive UTF-8 decoders fail to detect Unicode characters encoded multiple times. |
| | Best-fit (aliasing) | Characters not represented in the target character set may be replaced with a “best fit” character instead of the default character. For example, a fraction slash can become a normal slash. |
| | Normalization | Normalization is a converting a string segment to a unique, equivalent form. <br />Example: Normalizing composite character sequences into pre-composed characters such as 'a' + \` to 'à'.<br />More Information: [Unicode technical report TR15](http://www.unicode.org/unicode/reports/tr15/) |
| | Homograph attacks | Unicode equivalents from outside of ANSI script can be used to trick the user into going to a different site or server. Homograph attacks become a larger issue with introduction of International Domain Names (IDN). The basic example is writing `https://www.contoso.com` with a Cyrillic “o” or a zero.<br />[IDN homograph attack](https://en.wikipedia.org/wiki/IDN_homograph_attack) |
| **Date verification** | Using a formatted date for verification can fail with certain locales. | An algorithm that verifies expiration dates or time spans using a formatted date can be broken by changing the language settings. These problems are commonly seen on the Web. |
| **Risky APIs** | Dangerous APIs | An internet search will reveal the most recently documented risky APIs. |
| **Government requirements** | Risk of government non-compliance actions (fines, recalls)| Local governments may have their own specific requirements, such as the French Encryption Declaration (see [Encryption control - Agence nationals de la sécurité des systèmes d'information](https://www.ssi.gouv.fr/en/regulation/cryptology/)). You must be aware of these regulations. |
