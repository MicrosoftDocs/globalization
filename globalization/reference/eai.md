---
title: Email Address Internationalization (EAI)
description: Email Address Internationalization (EAI) resolves the lack of support for non-Latin scripts in email addresses.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:01/24/2024
---

# Email Address Internationalization (EAI)

Communication via email largely depends on three protocols:

- Simple Mail Transfer Protocol (SMTP), used for email transmission
- Post Office Protocol (POP), used to retrieve email from an email server
- Internet Message Access Protocol (IMAP), used to retrieve email from an email server

IMAP was designed to support online and offline client applications as compared to the older POP standard, which was designed for clients to retrieve then delete messages from the email server.

As defined in RFC 5322, SMTP email addresses have the form `local-part "@" domain`. The local-part was originally limited to upper- and lower-case letters from the Latin script, digits, and a handful of other printable characters (for example, the minus sign).

While email transmission depends on the RFC standards, email server providers have control over how email addresses are allocated. For example, even though RFC 5322 permits email addresses to use characters like the exclamation mark (U+0021), email servers might impose additional policies to restrict characters used in email addresses. For example, an email server might require addresses to only use Latin letters and digits. An email server might also support templates for creating multiple email addresses for a single user. For example, a recipient might want to receive an email regardless of whether their first and last names in their email addresses are separated by a dot.

Recipients typically want email addresses that are personally relevant, easy to remember, and easy for others to use. The restrictions on email addresses specified in RFC 5322 mean that recipients, where Latin script isn't used to represent their languages, can't use email addresses using characters from their typical script, and instead rely on transliterations. Email Address Internationalization (EAI) attempts to resolve the discrepancy in support for scripts other than Latin. A set of RFC documents ([RFC 6530](https://www.rfc-editor.org/rfc/rfc6530.txt), [RFC 6531](https://www.rfc-editor.org/rfc/rfc6531.txt), [RFC 6532](https://www.rfc-editor.org/rfc/rfc6532.txt), and [RFC 6533](https://www.rfc-editor.org/rfc/rfc6533.txt)) define the mechanisms and protocol extensions to enable the full support of Unicode characters in email addresses.

When using EAI, the local-part of the email address is still limited in the use of whether specific characters can appear outside of quotation marks as defined in RFC 5322. For example, an email address can't have more than one unquoted @ character, which is used to separate the local-part and the domain. The domain must comply with [International Domain Name](idn.md) (IDN) standards, which are mandated by the registrars of top-level domains, such as country-code top-level domains.

Support of EAI is largely dependent on the email server. For example, an email server might support sending emails to an address using EAI; however, the same email server doesn't have to support hosting EAI email addresses.
