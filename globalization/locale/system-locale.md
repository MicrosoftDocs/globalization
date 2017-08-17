---
title: System Locale
description: System locale specifies the default language to use for non-Unicode programs. It's important to understand this to globalize the software.
ms.assetid: 3d2fae5d-2ed2-47f2-94e5-ce3d45cc02fe
ms.date: 02/23/2017
---
# System Locale

The system locale determines which code page is used on the system by default on operating systems that use Unicode as their native encoding-such as Windows 2000 and Windows XP-to convert text data from Unicode to code page whenever dealing with legacy non-Unicode applications. In fact, in Windows XP the system locale is called "Language for non-Unicode programs." Only applications that do not use Unicode as their default character-encoding mechanism are affected by this setting; therefore, applications that are already Unicode-encoded can safely ignore the value and functionality of this setting. (See Figure 2.) Support for new scripts in Windows 2000 and Windows XP (such as for the Indic family, Armenian, and Georgian languages) has been provided through Unicode encoding and, therefore, these scripts are also free of any system-locale limitations.

In this example, the system locale has been set to Romanian (Windows code page 1250 and Original Equipment Manufacturer \[OEM\] code page 852), a Central European language. This means that all Central European-language applications that are based on code pages can run safely in this configuration, since they are part of the same language collection.

So, for example, a Polish application (another Central European language) does not need a system-locale change. Also, since English is part of the invariant American Standard Code for Information Interchange (ASCII) range of all code pages, English legacy applications will always run properly.

Sometimes there is no noticeable difference between two system locales. For example, the German (Standard) and German (Austria) system locales are identical, since they share the same OEM and Windows code pages; therefore, the behavior of non-Unicode-based applications will be identical in both scenarios. In general, system locales of a language group are very similar and might only be different in the OEM code page.

As its name suggests, the system locale is a unique setting for each system. Only an administrator has the right to change the system locale, and the computer will need to be restarted in order for changes to take effect. The administrator can only select a system locale if the appropriate language group-and its associated script support-is installed.

The system locale is a system variable that cannot be changed programmatically. The only way to change it is for an administrator to do so manually.


