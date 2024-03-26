---
title: Responsive user interface
description: An adaptive user interface is one in which the UI elements can be resized and repositioned dynamically and automatically based on factors including screen orientation and screen size.
ms.date: 3/26/2024
author: jowilco
---

# Responsive user interface

User interfaces for Win32 applications are implemented via the Microsoft Windows [Resource Compiler](/windows/win32/menurc/resource-compiler) and its associated [resource files](/windows/win32/menurc/about-resource-files), containing controls like [DIALOGEX](/windows/win32/menurc/dialogex-resource). These types of controls are typically positioned using a coordinate system with a specified height and width. Coordinate-based systems like this are problematic for localization. When translating text into different languages, it is unlikely that the translated text is the same length once rendered into the UI control. If the translated text is longer than the area specified for the original source text, the translated text would be truncated. You must resize and reposition UI controls to display the full length of the translated text.

Largely due to the proliferation of mobile devices, responsive design techniques are now best-practice for implementing UIs and documents. Frameworks such as [.NET Multi-platfom App UI](/dotnet/maui/what-is-maui) (MAUI) allow you to develop applications that can run on Android, iOS, macOS, and Windows devices from a single shared code base. To support all the form factors for these devices, flexible layouts allow developers to implement UIs where the layout changes depending on the screen size.

One of the advantages of these responsive design techniques for localization is that controls like [Label](/dotnet/api/microsoft.maui.controls.label) and [Button](/dotnet/api/microsoft.maui.controls.button) can resize or wrap depending on the length of the text. In general, you should not need to change dimensions once translated strings are available for your UI. However, it is still best practice to test for text expansion using techniques like [pseudolocalization](../methodology/pseudolocalization.md). For more information about text for UI controls, see [Message formatting](../internationalization/message-formatting.md).
