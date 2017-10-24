---
title: Input Locale
description: Legacy information regarding the input on the older versions of Windows.
ms.assetid: f8cdaa0d-69f9-4e03-8678-81d875f83c1a
ms.date: 02/23/2017
---


# Input Locale

Known as "input locale" in Windows 2000 and "input language" in Windows XP, this variable describes a language a user wants to enter into an application (not necessarily type) and the method of input. There can be multiple input locales installed and the user can switch between them. The default input locale is the locale that is active when a new application is started (or in some applications, when a new window is opened). Switching to a different input locale is done on a per-thread basis; that is, you can have two different input locales in two different applications.


