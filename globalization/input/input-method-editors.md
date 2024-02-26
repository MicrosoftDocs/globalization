---
title: Input Method Editors (IME)
description: Due to the large number of characters in some languages, special input methods are required to enter text. Some languages have an Input Method Editor (IME) for entering text.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Input Method Editors (IME)

Some languages, such as Japanese, Korean, and Chinese, use thousands of characters that can't be easily typed with a typical keyboard with 101-105 keys, which has a separate key for each letter. Input Method Editors (IME) let users enter such characters by typing a combination of keystrokes or making a sequence of mouse operations. An IME can support both [hardware and software keyboards](keyboards.md).

An IME can be part of the operating system or a separate app. Windows comes with more than 20 IMEs. For the complete list, see [Keyboard identifiers and input method editors for Windows](/windows-hardware/manufacture/desktop/windows-language-pack-default-values).

Your app doesn’t need to interact directly with an IME. It works as part of the system regardless, like a software keyboard. You should test the text entry user experience of your app with the IME, so you can fix any UI issues, such as the IME UI obscuring a part of your app or vice versa. Another thing to be wary of is keystroke detection. Since keystrokes don't correspond directly to characters when an IME is used, feature such as autocomplete need to be tested carefully.

## Requirements for third party IMEs

If you don’t want to use the built-in Windows IMEs, it’s possible to create your own custom IME. They have three main requirements:

- It must be digitally signed.
- It must be [Text Services Framework (TSF)](/windows/win32/tsf/text-services-framework) aware and have the appropriate IME flags set correctly.
- It must follow the guidelines and requirements described in [Custom Input Method Editor (IME) requirements](/windows/apps/design/input/input-method-editor-requirements) and [Design and code Windows apps](/windows/apps/design/).

If these requirements aren't met, Windows blocks the IME from running and the IME might also be removed from the system by Windows Defender.
