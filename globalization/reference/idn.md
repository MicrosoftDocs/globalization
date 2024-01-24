---
title: Internationalized Domain Names (IDN)
description: Understand the basics of Internationalized Domain Names (IDN) and how they are managed within the Domain Name System (DNS).
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Internationalized Domain Names (IDN)

Domain Name System (DNS) is an industry-standard suite of protocols that comprise TCP/IP, and enables computer name-to-IP address mapping name resolution. When a user enters a DNS name in an application such as a web browser, DNS services can resolve the name to other information that is associated with the name, such as an IP address. For example, a URL like `https://learn.microsoft.com` is mapped to a specific IP address, base. The URL is much easier for users to remember than the corresponding IP address. The foundation of the URL is the Top-Level Domain (TLD) (`.com`) and the domain name (`microsoft`). The [Internet Assigned Numbers Authority](https://www.iana.org/) (IANA) is the organization that coordinates how domain names and IP addresses are managed.

There are various types of TLD’s, including:

- Generic top-level domain (gTLD), such as `.com`, maintained by IANA.
- Sponsored top-level domains (sTLD), such as `.edu` which is sponsored by US institutions of higher education
- Country code top-level domain (ccTLD), such as `.cn` for the People’s Republic of China
- Internationalized country code top-level domain (IDN ccTLDs), such as `.中国` also for the People’s Republic of China.

A second-level domain (SLD or 2LD) is a domain directly below a TLD. Domain registration is typically handled by country or regional domain name registrars. Domain name registrars can be governmental, non-profit, or commercial organizations licensed by a gTLD or ccTLD registry and who are responsible for registering domain names within the scope of the TLD. While IANA manages coordination of how domain names are managed, the TLD registrars have a lot of control over the rules and requirements for registering SLDs. For example, registries can restrict the second level under the TLD to a set of pre-determined SLDs. In the United Kingdom, `.co.uk`  is used for commercial organizations, while `.ac.uk`  is used for academic institutions.

Domain names were originally restricted to ASCII characters; however, internationalized domain names (IDNs) were created to enable support for a broad range of scripts. Users worldwide can now use meaningful domain names without having to transcribe the names using Latin characters.

Like requirements for SLDs, TLD registrars can also place limits on naming conventions for IDNs. These limits include:

- Restrictions on the characters that can be used
- Whether characters from more than one script can be used in a label
- Which characters can appear adjacent to each other
- The length of each label

While IDN enables the support of domain names using scripts other than Latin, these domain names are stored in DNS as ASCII strings using [Punycode](https://www.rfc-editor.org/rfc/rfc3492.txt) transcription. Web browsers can convert between the visual representation of the domain using Unicode characters and the Punycode equivalent used by DNS. Note that [DNS requires](https://www.rfc-editor.org/rfc/rfc2181) that any label is limited to 63 octets (63 bytes on an 8-bit system) and the domain name is limited to 255 octets. These limits are imposed on the Punycode transcription of the labels, not the original Unicode characters.

## IDN and Security

Domain name spoofing is a type of [phishing attack](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44) where the attacker is trying to direct users to visit a website by using a domain name that is similar in appearance to the user’s intended website. One way of achieving this effect is for the attacker to register domains using characters with similar appearance to the original domain. For example, the Latin letter o (U+006F LATIN SMALL LETTER O), the Greek letter ο (U+03BF GREEK SMALL LETTER OMICRON) and the Cyrillic letter о (U+043E CYRILLIC SMALL LETTER O) all have a similar appearance (homoglyphs). An attacker could try to register a domain with either the Greek or Cyrillic character replacing one or both of the Latin letter “o”s in microsoft for the domain `microsoft.com`. For more information about spoofing attacks and Unicode security considerations, see [Unicode Technical Report #36](https://www.unicode.org/reports/tr36/).

There are several strategies for mitigating these types of attack, including:

- Server-side:
  - Domain name registries can limit mixed-script domain names.
  - Domain owners can register domain names with common misspellings and variations, including homoglyphs.
- Client-side:
  - Browsers can display the Punycode version of the domain when a domain name spoofing attack is suspected.

For more information about mechanisms to detect security issues with IDNs and Unicode, see [Unicode Technical Standard #39](https://www.unicode.org/reports/tr39/).
