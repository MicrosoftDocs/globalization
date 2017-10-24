---
title: Layout
description: 
ms.assetid: 1c7c3814-4297-4d1d-a2f1-642687aa917b
ms.date: 03/16/2016
---


# Layout

Another element that requires localization is the UI layout. The localization process changes the UI layout because the length of the translated text usually increases from its original length. This text-stretching affects the size of the UI controls that display the text and potentially necessitates relocating and resizing the UI controls. The best way to ensure that the UI has a consistent look and feel throughout different localized versions is for the development team to design the UI with resizing-and other required locale variances-in mind from the beginning. In turn, the localization team should try to minimize any changes to the UI, unless these changes are absolutely necessary.

In addition to text that increases in length when it is translated, font size can differ among language groups. For instance, East Asian languages usually display text in a larger font size than many other language groups. As a result of the change in font size, the system expands the UI vertically. Edit boxes, static text, and button controls within the East Asian localized version of the product usually result in larger vertical spacing than those within products from other language groups. Bidirectional languages like Arabic and Hebrew require mirroring of the screen layout to accommodate their RTL reading order. This requires mirroring the layout of menus, text, dialog boxes, and edit boxes.


