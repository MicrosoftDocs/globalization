---
title: Mirroring
description: Complex scripts refer to the languages, where the characters are not laid out in the left-to-right progression, as most European characters are.
ms.assetid: 437a9601-a54c-4c91-bb64-52c4d1b62e86
ms.date: 04/26/2017
---
# Mirroring

For right-to-left (RTL) languages, not only does the text alignment and text reading order go from right to left; UI elements should follow this natural direction of right to left. By default, edit controls inserted into a right-to-left document should inherit right-to-left behavior. Control handles and pull-down buttons should be mirrored on right-to-left documents.

In localized applications for right-to-left languages, menus and submenus are mirrored and appear on the right side of the application. The figure below shows the Outlook UI for Arabic, which is mostly a mirror of the LTR UI. For example, the menu starts from the right side of the screen instead of from the left.

![How the User Interface for Arabic compares to English language](/media/hubs/globalization/IC868515.jpg "How the User Interface for Arabic compares to English language")

**How the User Interface for Arabic compares to English language.**

### Exceptions to RTL Reading Order and Alignment

In general, all controls for right-to-left (RTL) languages (e.g., Arabic and Hebrew) are right-aligned and have a right-to-left reading order; if a scroll bar is required, it will appear on the left side of the control. However, some edit controls are left aligned and have a left-to-right (LTR) reading order—and the scroll bar for the control will appear on the right-side—since their content is in a non-RTL language or causes other issues when mirrored. These exceptions are:

-   File names and paths
-   Printer names and paths
-   IRI, URIs, URLs, and UNCs
-   Server and Domain names
-   Media controls

