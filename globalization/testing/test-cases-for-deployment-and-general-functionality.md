---
title: Test Cases for Deployment and General Functionality
description: Globalization test cases for deployment and functionality.
ms.assetid: 98643fba-eb93-4fd3-9604-b35aef27c61a
ms.date: 04/11/2017
---

# Test Cases for Deployment and General Functionality

|**Areas and Items to Test**|**Details**|**Applicability**|
|---|---|---|
|Application setup under different language environments|Install on a platform where the UI language of the operating system does not match the language of the application; verify with different language settings that do not match. Verify the ability of the application to work with localized operating-system objects. Choose a language that is deeply localized. If the application implements an language-switching behavior, make sure its UI language follows the UI language of the operating system.|All applications; if the application implements language-switching functionality, make sure the default UI language of the application follows the UI language of the operating system.|
|General functionality with various language settings|Verify that the code does not have unwanted language settings dependencies.|All applications|
|Uninstalling the application with different language settings|Make sure that language settings that were active when the application was installed are different from those set at the time when the application is uninstalled.|All applications|
|For legacy systems: Application setup on an operating system with MUI installed and where user's default UI language is different from English|Verify the behavior in a multilingual environment where the UI language is defined by rules different from those of the older systems. Change the system and user locales to verify multilingual abilities of the UI.|All applications; applications that implement MUI behavior must undergo testing that is even more extensive.|
|For legacy systems: Multiplatform installation|Applications that need to be installable on multiple platforms should call code page-based code for installation on downlevel platforms. Make sure the UI that is displayed is not compromised on platforms with nondefault language settings. Unicode-based applications must work properly with different system-locale settings. No change in the user-locale settings or the user's UI language preferences should cause functionality or display problems.|Applications that target downlevel platforms or communicate with legacy systems|
