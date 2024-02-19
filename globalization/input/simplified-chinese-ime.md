---
title: Simplified Chinese IME
description: Installing and using the Simplified Chinese Input Method Editor (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Simplified Chinese IME

If you need to enter some text in Simplified Chinese, the Microsoft Pinyin IME for Windows lets you enter text using Simplified Chinese characters while using a typical keyboard with 101-105 keys and keeping English as your Windows display language.

## Add the Simplified Chinese keyboard layout

To add the Simplified Chinese keyboard layout to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Chinese (Simplified, China)** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. For entering Simplified Chinese text while keeping English as your Windows display language, none of them are necessary. When you are happy with your choices, select **Install**.

By default, Simplified Chinese is installed with the Microsoft Pinyin IME, based on the phonetic pinyin method of romanization (converting text to the Latin script). A Microsoft Wubi IME is also available, but it’s not covered in this article.

## Type Simplified Chinese text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (those in the **Preferred languages** list in Settings) by pressing the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This can be faster if you have more than two languages installed.

IMAGE

To type text using Simplified Chinese, do the following:

1. Select **Chinese (Simplified, China)**. The system tray now shows **拼** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英)**, press the Shift key or select the input mode icon.
1. Start typing the Simplified Chinese character or word using its phonetic pinyin transcription. The conversion candidate window opens and shows matches for what you have typed. You can keep typing and the candidate window updates in real time. See the [example](#example) at the end of this article.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Spacebar to select the currently focused candidate
    - Tab key to expand the window and show text suggestions from Bing
    - Number keys to quickly select the corresponding candidate
    - Enter to close the window without making a selection, but keeping the text you entered
    - Esc to close the window without making a selection and deleting the text you entered

## Use the right-click menu for additional options

When the Simplified Chinese keyboard layout is active, you can right-click the input mode icon (**中** or **英**) to access various options. The right-click menu also has a shortcut to **Microsoft Pinyin** settings. You can change many settings related to using the IME:

- Pinyin style, reading auto-correction, super abbreviated pinyin, IME default modes, and fuzzy pinyin rules
- [Keyboard shortcuts](#configure-keyboard-shortcuts)
- Appearance of the candidate window
- Lexicon and self-learning settings
- Various advanced settings

For more information about these settings, see [Microsoft Simplified Chinese IME](https://support.microsoft.com/en-us/windows/microsoft-simplified-chinese-ime-9b962a3b-2fa4-4f37-811c-b1886320dd72#ID0EBD=Microsoft_Pinyin).

### Change character width

The Simplified Chinese IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

### Change character set

You can change between Simplified and Traditional characters while using the Simplified Chinese IME. To change the character set, open the right-click menu and select **Character set** > **Simplified** or **Traditional**.

### Enter emoji and symbols

To quickly insert emoji, kaomoji (Japanese-style ASCII emoji), GIFs, and symbols such as currency or mathematical symbols, open the right-click menu and select **Emoji & symbol**. In the dialog that opens, items are sorted into tabs by type and category, and your most recent selections are shown on the first tab. Select an item to insert it into your text.

### Store commonly used phrases

You can store phrases that you need to enter frequently. To do so, open the right-click menu and select **User defined phrases**. This opens the related page in Settings. You can add and order phrases individually. A quick way to add many phrases is to import them from a text file where each phrase is on a separate line.

### Select which domain lexicon to use

To select which subjects have their specialized vocabulary included in the conversion candidates, open the right-click menu and select **Domain lexicon**. This opens the related page in Settings. You can select the subjects individually or switch off the whole domain lexicon feature.

### Configure keyboard shortcuts

If you want to change the keyboard shortcuts for working with the Simplified Chinese IME, open the right-click menu and select **Key configuration**. This opens the related page in Settings. You can choose the keys for various mode switches and candidate navigation.

### Use the IME toolbar to access options

To open the IME toolbar, open the right-click menu and select **IME toolbar**. It gives you another way to access some of the options discussed in this article.

- You can switch the input mode.
- You can change between half-width and full-width characters.
- You can change between Chinese and English punctuation.
- You can change between Simplified and Traditional Chinese characters.
- You can open the [Emoji & symbol](#enter-emoji-and-symbols) dialog.
- You can open the **Microsoft Pinyin** settings page and customize the toolbar itself.

## Example

The Simplified Chinese word for summer is 夏天. It consists of two characters whose pinyin romanizations are “xia” and “tian”.

To type the word, select the Simplified Chinese keyboard layout from the system tray and change to Chinese input mode, if necessary. Then start typing the pinyin word. The candidate window opens as you type. Do not press Spacebar after “xia”, as that would select the currently focused candidate, which might not be the right character.

After you have typed “xiatian,” you can see how the IME has changed the spelling to “xia’tian” and the correct candidate is displayed as the first one. Press Spacebar to insert it into your text.
