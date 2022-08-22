---
title: Mirroring
description: Complex scripts refer to the languages, where the characters are not laid out in a simple left-to-right progression.
ms.date: 04/26/2017
---
# Mirroring

For right-to-left (RTL) languages such as Arabic and Hebrew, not only does the text alignment and text reading order go from right to left:
user interface elements should also follow the natural direction of right to left.
By default, edit controls in a right-to-left document should inherit right-to-left behavior.
Control handles and pull-down buttons should be mirrored on right-to-left documents.

In localized applications for right-to-left languages (more properly termed bi-directional languages or BiDi), menus and submenus are mirrored and appear on the right side of the application.
Figure 1 below shows the Outlook UI for Arabic, which is mostly a mirror of the left-to-right user interface.
For example, the menu starts from the right side of the screen instead of from the left.

![How the User Interface for Arabic compares to English language](./images/Mirroring.jpg "How the User Interface for Arabic compares to English language")

**Figure 1:** How the user interface for Arabic compares to English language

## Exceptions to right-to-left reading order and alignment

In general, all controls for right-to-left (RTL) languages are right-aligned and have a right-to-left reading order.
If a scroll bar is required, it appears on the left side of the control.
However, some edit controls are left aligned and have a left-to-right (LTR) reading order since their content is in a non-RTL language or causes other issues when mirrored.
For these controls, the scroll bar appears on the right-hand side.

These exceptions are:

- File names and paths
- Printer names and paths
- IRI, URI, URL, and UNC names
- Server and domain names
- Media controls
