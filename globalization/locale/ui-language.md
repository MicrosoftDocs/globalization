---
title: User interface language
description: Users want to be able to select the main user interface language and sometimes additional languages as well.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 01/10/2023

---

# User interface language

Users of a globalized system expect that they can select the language they prefer for the user interface of the operating system (OS) and applications they run on it. The default language will typically be determined by the language selected during the installation or will be specified by the operating system or browser. Users might need to change the language later. Additional languages may come preinstalled, or users may need to download and install language packs to have support for the languages they need. Multilingual users might even want to have several languages enabled in the system at once.

Users may want to use applications in a language that is different than the operating system language. For example, Windows 11 supports a "Windows display language" and one or more "Preferred languages". The selected Windows display language is the language Windows uses for its core features such as Settings and File Explorer. Preferred languages are an ordered list that Microsoft Store apps use: they appear in the first language on the list that a given app supports.

Application developers must make a choice for the applications that they produce. An application can default to the OS display language, the “preferred language,” or the language/locale set in the user’s browser (for applications that run inside a browser). An app could also have its own language settings that are independent from any of the operating system or browser settings.
