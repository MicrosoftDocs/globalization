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

## Types of keyboard shortcuts

Keyboard shortcuts are keystrokes, *key sequences*, or *key combinations* that provide an alternative way to do something that you’d typically do with a mouse. A key sequence consists of keys that are selected sequentially, while a key combination consists of two or more keys that are selected simultaneously.

[Keyboard shortcuts in Windows](https://support.microsoft.com/en-us/windows/keyboard-shortcuts-in-windows-dcc61a57-8ff0-cffe-9796-cb9706c75eec) provides a list of shortcuts for various common tasks. Keyboard shortcuts can vary depending on your locale, and the page is available in multiple languages. The two types of keyboard shortcuts in Windows and Windows applications are *access keys* and *shortcut keys*. An access key is a key sequence that users select to access UI controls that have text labels. A shortcut key is a key or key combination that users select to perform a common action without needing to navigate the UI.

[Access keys](/windows/apps/design/input/access-keys) are key sequences that consist of the Alt key and one or more alphanumeric keys. They're often accompanied by *key tips*, which are visual cues or badges displayed next to supported UI controls when you select the Alt key. Microsoft Office apps have extensive support for access keys. For example, if you select Alt+F, P in Outlook, the Print view opens. For more information, see [Access keys](/windows/apps/design/input/access-keys).

Shortcut keys include *[keyboard accelerators](/windows/apps/design/input/keyboard-accelerators)* (or accelerator keys). Accelerators are key combinations that consist of two kinds of keys: modifiers and nonmodifiers. Modifier keys include, for example, Shift and Ctrl. Nonmodifier keys include, for example, all alphanumeric keys, Delete, and Spacebar. A common example of an accelerator is Ctrl+A, which typically selects all items or all text. For more information, see [Keyboard accelerators](/windows/apps/design/input/keyboard-accelerators).

For a general audience, you should use the term *keyboard shortcuts* in your app and its documentation and any other support material. If you have content that is aimed at developers or discusses customizing your app’s UI, you can use the terms *access keys* and *shortcut keys* to distinguish between the two.

## Localizing keyboard shortcuts

Shortcut keys typically use either the first character of the action name or another relevant character that helps with recall. When the names of actions are localized, you should also update the shortcut keys to maintain the ease of use. For more information, see [Localize access keys](/windows/apps/design/input/access-keys#localize-access-keys) and [Localize the accelerators](/windows/apps/design/input/keyboard-accelerators#localize-the-accelerators).

For a target language that uses a non-Latin writing system that requires an [input method editor (IME)](input-method-editors.md), such as Japanese, it's best to use the original keyboard shortcuts.

Actions, such as saving a file, copying text or applying bold formatting, are common across many applications. By convention, applications in a single language use the same shortcut for the same action. Applications in a language other than English might use a different shortcut than the English shortcut but be consistent in the use of that shortcut. For example, the shortcut for applying bold formatting is **Ctrl + B** in English and **Ctrl + G** in French.

Localizing keyboard shortcuts involves planning:

- You need to expose your app's shortcuts to localization.
- You need to provide sufficient guidance to localization. This includes:
  - Coordinating between development and localization to ensure that the end-to-end localization process can support the adaptation of keyboard shortcuts.
  - Ensuring that the localization team has enough context to determine what is the appropriate shortcut for a given translated string and how to set it.
  - Establishing a process with clear ownership to ensure correct and functional shortcuts at runtime.
- You need to verify that the shortcuts are functional, match the localized UI, and aren't duplicated in a given part of the UI.

An experienced localization team or supplier can typically help a development team navigate these challenges, if they're engaged early.
