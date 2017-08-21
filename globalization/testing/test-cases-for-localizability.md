---
title: Test Cases for Localizability
description: Localizability test cases.
ms.assetid: 330ea2d5-defe-464b-986d-b06a0dd595f4
ms.date: 04/12/2017
---

# Test Cases for Localizability

|**Areas and Items to Test**|**Details**|**Applicability**|
|---|---|---|
|Isolation of the localizable resources|Ensure all UI elements are isolated in the localizable resources. Pseudo-localization should not leave any unlocalized text in the UI. Text that remains untranslated after pseudo-localization most likely is hard-coded in the application's code and creates a localizability problem. In addition to the text that appears in the graphical user interface (GUI), verify that the following text is localizable: parts of the command-line interface; messages in the Event Log and Error Log; error messages; and tool tips.|Applications that use text from external resources|
|Locale-independent handling of resources|Check that static UI text (such as names of dialog boxes, field labels, tabs, and other things the user cannot change) is displayed in the language of the application's UI. There should be no question marks, default glyphs, or random characters in the UI, regardless of the locale or language settings of the system.|Applications that use separate resource modules for UI text storage|
|Handling of string dependencies|Applications should not rely on consistency of the resource text in different parts of the system. If the functionality of an application relies on several strings being identical in different parts of the application, either those strings have to originate from a single source, or their relationship should be clearly commented for future localization and support. Make sure that random pseudo-localization does not affect the functionality of the application.|Applications that display UI text from external resources|
|Language-independence of some elements|Names of some elements (such as Help files, satellite DLLs, IRIs, database files, field names and other code elements, etc.) that the application uses should not be localized; pseudo-localization should not change them. If pseudo-localization were to change these names, applications wouldn't be able to find their databases.|Applications that open external files to perform some of their operations|
|Isolation of font properties|Font properties must not be in localizable resources. Applications violating this rule are likely to use an incorrect font face and size if pseudo-localized.|Applications that display text in the GUI|
|Font-size and display-resolution independence|Verify that applications are not affected if the size of the font or screen resolution is changed.|All applications|
|Localization-independent functionality|Ensure pseudo-localization doesn't affect the following areas: hot keys, keyboard shortcuts, and accelerators; menus; responses (such as \[Y|N\]) required by command-line applications; and other UI control elements. All of the areas just listed must be accessible on a localized platform, even if the input does not match the UI language of the application.|Applications that have control elements in the UI|
|UI adjustable to the UI text growth|Growth of the UI text length due to pseudo-localization should not cause text clipping; compensate for this problem by having the UI adjusted automatically (recommended with pseudo-localization) or manually (by localizers). |Applications should not assume the UI dimensions are fixed.|Applications that display text in the GUI|
|Mirroring-awareness in UI composition|Dynamic placement of UI elements might cause the following mirroring problems, seen after pseudo-mirroring is applied: misplaced controls in dialog boxes; broken check-box display; empty property pages displayed in property sheets; incorrect text alignment; mirroring of the text (text displayed in reverse order); and display not matching the real location of the control (controls are drawn in one place but actually work in another).|All applications|
|Localizability of non-textual resources|For all non-textual resources (such as images and sounds) that must be localized, make sure clear rules and requirements are defined for the localization.|Applications that incorporate localizable non-textual resources|
|Run-time string composition|Verify that the dynamic-string composition can hold if the order of parts of the output must be changed. Make sure the composition rules are not based on a single language.|Applications that build strings from pieces at run time|
|Dynamic retrieval of system-defined names|The applications should not refer to built-in objects of the operating system by names stored in the application: the names of built-in accounts such as "Administrator" or folders such as "Program Files" must be retrieved dynamically. To check this, pseudo-localize the application and run it on a localized platform.|All applications|


