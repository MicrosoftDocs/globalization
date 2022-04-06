---
title: Test cases for deployment and general functionality
description: This article outlines some globalization test cases for deployment and functionality.
---

# Test cases for deployment and general functionality

* Install on a platform where the user interface language of the operating system does not match the language of the application.

* Make sure that language settings that were active when the application was installed are different from when the application is uninstalled.

* Choose languages that are fully localized in the system and the application.

* On Windows, use Windows Language settings with the system language different from the user language.
This helps uncover issues where different parts of the application are using inconsistent settings.

* Verify the ability of the application to work with localized operating-system objects (special folders, account names, registry entries).

* If the application implements language switching, make sure its default UI language follows the default user language from the operating system.

* Verify that the code does not have unwanted dependencies on language settings.
