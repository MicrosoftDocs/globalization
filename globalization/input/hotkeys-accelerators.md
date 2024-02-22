---
title: Keyboard shortcuts and localization
description: The definition of hotkeys and accelerators should take international keyboards into account.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Keyboard shortcuts and localization

Windows and Windows applications use keyboard shortcuts to improve the usability and the accessibility of your applications by providing an alternative way of navigating using your keyboard instead of a pointer device (such as touch or mouse).

Keyboard shortcuts are keystrokes, *key sequences*, or *key combinations* that provide an alternative way to do something that you’d typically do with a mouse. A key sequence consists of keys that are selected sequentially, while a key combination consists of two or more keys that are selected simultaneously.

[Keyboard shortcuts in Windows](https://support.microsoft.com/en-us/windows/keyboard-shortcuts-in-windows-dcc61a57-8ff0-cffe-9796-cb9706c75eec) provides a list of shortcuts for various common tasks. Keyboard shortcuts can vary depending on your locale, and the page is available in multiple languages. The two types of keyboard shortcuts in Windows and Windows applications are *access keys* and *shortcut keys*. An access key is a key sequence that users select to access UI controls that have text labels. A shortcut key is a key or key combination that users select to perform a common action without needing to navigate the UI.

[Access keys](/windows/apps/design/input/access-keys) are key sequences that consist of the Alt key and one or more alphanumeric keys. They're often accompanied by *key tips*, which are visual cues or badges displayed next to supported UI controls when you select the Alt key. Microsoft Office apps have extensive support for access keys. For example, if you select Alt+F, P in Outlook, the Print view opens. If you have an app that is localized into other languages, you should think about localizing any access keys as well. For more information, see [Localize access keys](/windows/apps/design/input/access-keys).

Shortcut keys include *[keyboard accelerators](/windows/apps/design/input/keyboard-accelerators)* (or accelerator keys). Accelerators are key combinations that consist of two kinds of keys: modifiers and nonmodifiers. Modifier keys include, for example, Shift and Ctrl. Nonmodifier keys include, for example, all alphanumeric keys, Delete, and Spacebar. A common example of an accelerator is Ctrl+A, which typically selects all items or all text. We recommend localizing all your app accelerators too. For more information, see [Localize the accelerators](/windows/apps/design/input/keyboard-accelerators).

There's one exception to these localization recommendations. If the localization target language uses a non-Latin writing system that requires an [input method editor (IME)](input-method-editors.md), such as Japanese, it's best to use the original keyboard shortcuts.

For a general audience, you should use the term *keyboard shortcuts* in your app and its documentation and any other support material. If you have content that is aimed at developers or discusses customizing your app’s UI, you can use the terms *access keys* and *shortcut keys* to distinguish between the two.
