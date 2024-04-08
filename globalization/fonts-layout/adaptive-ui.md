---
title: Responsive user interface
description: Implement responsive design techniques to support localization for text in UI controls.
ms.date: 3/26/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:03/26/2024
---

# Responsive user interface

Historically, user interfaces were specified using a coordinate system with a specified position, height, and width for each control. For example, user interfaces for Win32 applications are implemented via the Microsoft Windows [Resource Compiler](/windows/win32/menurc/resource-compiler) and its associated [resource files](/windows/win32/menurc/about-resource-files), containing controls like [DIALOGEX](/windows/win32/menurc/dialogex-resource). Coordinate-based systems like this are problematic for localization. When translating text into different languages, it's unlikely that the translated text is the same length once rendered into the UI control. If the translated text is longer than the area specified for the original source text, the translated text would be truncated. You must resize and reposition UI controls to display the full length of the translated text.

Largely due to the proliferation of mobile devices, responsive design techniques are now best-practice for implementing UIs and documents. Frameworks such as [.NET Multi-platfom App UI](/dotnet/maui/what-is-maui) (MAUI) allow you to develop applications that can run on Android, iOS, macOS, and Windows devices from a single shared code base. To support all the form factors for these devices, flexible layouts allow developers to implement UIs where the layout changes depending on the screen size.

One of the advantages of these responsive design techniques for localization is that controls like [Label](/dotnet/api/microsoft.maui.controls.label) and [Button](/dotnet/api/microsoft.maui.controls.button) can resize, wrap, or move depending on the length of the text, without need to manually adapt positions and dimensions for each language. To achieve this, a best practice is to test for text expansion using techniques like [pseudolocalization](../methodology/pseudolocalization.md). For more information about text for UI controls, see [Message formatting](../internationalization/message-formatting.md).
