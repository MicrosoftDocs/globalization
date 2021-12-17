---
title: Layout
description: Another element that requires localization is the UI layout.
ms.assetid: 1c7c3814-4297-4d1d-a2f1-642687aa917b
ms.date: 03/16/2016
---

# Layout

Localization must also consider the user interface layout.
The localization process changes the user interface layout because the length of the translated text usually increases from its original length.
This text-stretching affects the size of the user interface controls that display the text and potentially necessitates relocating and resizing the controls.
The best way to ensure that the user interface has a consistent look and feel throughout different localized versions is for the development team to design the user interface from the beginning with resizing-and other required locale variances in mind.
In turn, the localization team should try to minimize changes to the user interface unless these changes are absolutely necessary.

In addition to text that increases in length when it is translated, font size can differ among languages.
For instance, East Asian languages usually display text in a larger font size than many other languages.
As a result of the change in font size, the system expands the user interface elements vertically.
Edit boxes, static text, and button controls within the East Asian localized version of the product usually result in larger vertical spacing than in other languages.
Bidirectional languages like Arabic and Hebrew require mirroring of the screen layout to accommodate their right-to-left reading order.
This requires mirroring the layout of menus, text, dialog boxes, and edit boxes.
