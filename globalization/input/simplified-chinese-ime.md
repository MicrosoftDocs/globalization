---
title: Simplified Chinese IME
description: Installing and using Simplified Chinese Input Method Editors (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Simplified Chinese IMEs

If you need to enter some text in Simplified Chinese, the Microsoft Pinyin Input Method Editor and the Microsoft Wubi Input Method Editor (IME) for Windows lets you enter text using Simplified Chinese characters while using a typical keyboard with 101-105 keys. Using either IME doesn't require changing your current Windows display language.

## Add support for Simplified Chinese input

To add support for Simplified Chinese input to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Chinese (Simplified, China)** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. If you want to enter Simplified Chinese text while keeping English as your Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

By default, Simplified Chinese support is installed with the Microsoft Pinyin IME, based on the phonetic Pinyin method of romanization (converting text to the Latin script). You can also use the Microsoft Wubi IME, which enables you to use the structure of characters to input text. Each Simplified Chinese character can be decomposed to one or more *root characters*, and the Wubi IME allows users to enter root characters to build up a final character. To install the Microsoft Wubi IME:

1. On the **Language & region** page, select the Options (**…**) icon next to **Chinese (Simplified, China)** and select **Language options**.
1. Select **Add a keyboard** and select **Microsoft Wubi**.

## Type Simplified Chinese text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (layouts in the **Preferred languages** list in Settings) by pressing the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

### To type text in Simplified Chinese using the Microsoft Pinyin IME

1. Select **Chinese (Simplified, China) | Microsoft Pinyin**. The system tray now shows **拼** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英)**, press the Shift key or select the input mode icon.
1. Start typing the Simplified Chinese character or word using its phonetic Pinyin transcription. The conversion candidate window opens and shows matches for what you typed. You can keep typing and the candidate window updates in real time.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Spacebar to select the currently focused candidate
    - Tab key to expand the window and show text suggestions from Bing
    - Number keys to quickly select the corresponding candidate
    - Enter to close the window without making a selection, but keeping the text you entered
    - Esc to close the window without making a selection and deleting the text you entered

### To type text in Simplified Chinese using the Microsoft Wubi IME

1. Select **Chinese (Simplified, China) | Microsoft Wubi**. The system tray now shows **五** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), press the Shift key or select the input mode icon.
1. The Wubi IME groups keys into regions based on the first stroke of the root characters. To enter a character, start by pressing the keys that correspond to the root character, followed by the keys that correspond to the remaining strokes. The candidate window opens and shows matches for what you typed.
1. Different characters can be composed of the same root characters. Wubi addresses this by using isolation keys to specify the configuration of the character. Enter the isolation key after the root characters to select the correct character as necessary.
1. The conversion candidate window allows you to choose the correct character.

### Use the right-click menu for additional options

When either Simplified Chinese IME is active, you can right-click the input mode icon (**中** or **英**) to access various options. The right-click menu also has a shortcut to **Settings** for additional options.

For Microsoft Pinyin, these settings include:

- Pinyin style, reading autocorrection, super abbreviated Pinyin, IME default modes, and fuzzy Pinyin rules
- [Keyboard shortcuts](#configure-keyboard-shortcuts-pinyin-ime-only)
- Appearance of the candidate window
- Lexicon and self-learning settings
- Various advanced settings

For more information about these settings, see [Microsoft Simplified Chinese IME](https://support.microsoft.com/en-us/windows/microsoft-simplified-chinese-ime-9b962a3b-2fa4-4f37-811c-b1886320dd72#ID0EBD=Microsoft_Pinyin).

For Microsoft Wubi, these settings include:

- Input mode
- Mixed input settings
- IME mode
- Candidate window settings

For more information about these settings, see [Microsoft Simplified Chinese IME](https://support.microsoft.com/en-us/windows/microsoft-simplified-chinese-ime-9b962a3b-2fa4-4f37-811c-b1886320dd72#ID0EBD=Microsoft_Wubi).

#### Change input mode (Pinyin and Wubi IMEs)

You can switch between Chinese and English input modes by pressing the Shift key or selecting the input mode icon in the tray. The icon changes to **中** for Chinese input and **英** for English input.

The Wubi IME also has a menu item for **Input mode** that lets you switch between **Chinese** and **English** input.

#### Change character width (Pinyin and Wubi IMEs)

Both Simplified Chinese IMEs allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

#### Change character set (Pinyin IME only)

You can change between Simplified and Traditional characters while using the Pinyin IME. To change the character set, open the right-click menu and select **Character set** > **Simplified** or **Traditional**.

#### Enter emoji and symbols (Pinyin and Wubi IMEs)

To quickly insert emoji, kaomoji (Japanese-style ASCII emoji), GIFs, and symbols such as currency or mathematical symbols, open the right-click menu and select **Emoji & symbol**. In the dialog that opens, items are sorted into tabs by type and category, and your most recent selections are shown on the first tab. Select an item to insert it into your text.

#### Store commonly used phrases (Pinyin and Wubi IMEs)

You can store phrases that you need to enter frequently. To do so, open the right-click menu and select **User defined phrases** to open the related page in Settings. You can add and order phrases individually. A quick way to add many phrases is to import them from a text file where each phrase is on a separate line.

#### Select which domain lexicon to use (Pinyin IME only)

To select which subjects have their specialized vocabulary included in the conversion candidates, open the right-click menu and select **Domain lexicon** to open the related page in Settings. You can select the subjects individually or switch off the whole domain lexicon feature.

#### Configure keyboard shortcuts (Pinyin IME only)

If you want to change the keyboard shortcuts for working with the Pinyin IME, open the right-click menu and select **Key configuration** to open the related page in Settings. You can choose the keys for various mode switches and candidate navigation.

#### Use the IME toolbar to access options (Pinyin and Wubi IMEs)

To open the IME toolbar, open the right-click menu and select **IME toolbar**. It gives you another way to access some of the options discussed in this article.

- You can switch the input mode.
- You can change between half-width and full-width characters.
- You can change between Chinese and English punctuation.
- You can change between Simplified and Traditional Chinese characters. (Pinyin IME only)
- You can open the [Emoji & symbol](#enter-emoji-and-symbols-pinyin-and-wubi-imes) dialog.
- You can open the **IME Settings** page or customize the toolbar itself.

## Example

### Type with the Microsoft Pinyin IME

The Simplified Chinese word for summer is 夏天. It consists of two characters whose Pinyin romanizations are “xia” and “tian.”

To type the 夏天 using Microsoft Pinyin, select **Microsoft Pinyin** from the system tray and change to Chinese input mode if necessary. Start typing the Pinyin word. The candidate window opens as you type. Don't press Spacebar after “xia”, as that would select the currently focused candidate, which might not be the right character.

After you type “xiatian,” you can see how the IME changes the spelling to “xia’tian” and the correct candidate is displayed as the first one. Press Spacebar to insert it into your text.

### Type with the Microsoft Wubi IME

The Simplified Chinese word for summer is 夏天. To enter the word using the Microsoft Wubi IME, select **Microsoft Wubi** from the system tray and change to Chinese input mode if necessary. The following table shows the characters, their decomposition, and the corresponding keystrokes that can be used to enter 夏天. The last keystroke (in parentheses) is an isolation key used to specify the configuration of the character.

| Character | Decomposition | Keystrokes |
|-----------|---------------|------------|
| 夏 | 丆目夂 | dht(u) |
| 天 | 一大 | gd(i) |
