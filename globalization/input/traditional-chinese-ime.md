---
title: Traditional Chinese IME
description: Installing and using the Traditional Chinese Input Method Editor (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Traditional Chinese IME

If you need to enter some text in Traditional Chinese, Windows includes several Input Method Editors (IMEs) to let you enter text using Traditional Chinese characters while using a typical keyboard with 101-105 keys and keeping English as your Windows display language.

This article discusses the Microsoft Quick and Bopomofo IMEs. Quick is also known as Simplified CangJie. It lets users enter a character’s first and the last stroke used in the full CangJie system and then pick a character from the conversion candidate window. Bopomofo (also known as Zhuyin) is a phonetic system. Users type the phonemes of the Chinese character.

## Add the Traditional Chinese keyboard layout

To add the Traditional Chinese keyboard layout to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Chinese (Traditional, Hong Kong SAR)** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. For entering Traditional Chinese text while keeping English as your Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

By default, Traditional Chinese is installed with the Microsoft Quick IME. To install the Microsoft Bopomofo IME:

1. On the **Language & region** page, select the Options (**…**) icon on the **Chinese (Traditional, Hong Kong SAR)** row and select **Language options**.
1. Select **Add a keyboard** and select **Microsoft Bopomofo**.

## Type Traditional Chinese text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (those in the **Preferred languages** list in Settings) by pressing the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

### Use the Quick IME

To type text using Traditional Chinese with the Quick IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Microsoft Quick** IME. The system tray now shows **速** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), press the Shift key or select the input mode icon.
1. Press the two keys that correspond to the first and the last CangJie stroke of the Traditional Chinese character. The conversion candidate window opens and shows matches for what you typed. See the [example](#type-with-the-quick-ime) at the end of this article.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Enter to select the currently focused candidate
    - Number keys to quickly select the corresponding candidate
    - Spacebar to move to the next page
    - Tab key to expand the list to a table that you can navigate with the arrow keys
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To select one of the candidates, press the Shift key + the corresponding number. If there's more than one page of suggestions, press the Spacebar to move to the next page.

Note that you need to switch on the **Prompt associated phrases of the input characters** setting to be able to use the associate phrase window. For instructions, see [Use the Quick IME right-click menu for additional options](#use-the-quick-ime-right-click-menu-for-additional-options).

### Use the Bopomofo IME

To type text using Traditional Chinese with the Bopomofo IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Microsoft Bopomofo** IME. The system tray now shows **ㄅ** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), press the Shift key or select the input mode icon.
1. Type the Traditional Chinese character or word using the phonetic Bopomofo symbols. After you have typed the symbols for the word, press the Down arrow key to open the conversion candidate window. It shows matches for what you typed.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Enter to select the currently focused candidate
    - Number keys to quickly select the corresponding candidate
    - Spacebar to move to the next page
    - Tab key to expand the list to a table that you can navigate with the arrow keys
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To select one of these candidates, press the Shift key + the corresponding number. If there is more than one page of suggestions, press the Spacebar to move to the next page.

Note that you need to switch on the **Prompt associated phrases of the input characters** setting to be able to use the associate phrase window. For instructions, see [Use the Bopomofo IME right-click menu for additional options](#use-the-bopomofo-ime-right-click-menu-for-additional-options).

## Use the Quick IME right-click menu for additional options

When the Traditional Chinese keyboard layout is active, you can right-click the input mode icon (中 or 英) to access various options. The right-click menu also has a shortcut to **Microsoft Quick** IME settings. You can change the following settings related to using the IME:

- Default input mode and other input settings
- Input assistance options, such as the use of the associate phrase window
- Character set options

### Change character width

The Quick IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

## Use the Bopomofo IME right-click menu for additional options

When the Traditional Chinese keyboard layout is active, you can right-click the input mode icon (**中** or **英**) to access various options. The right-click menu also has a shortcut to **Microsoft Bopomofo** IME settings. You can change the following settings related to using the IME:

- Default input mode and other input settings
- Input assistance options, such as the use of the associate phrase window
- Keyboard shortcuts
- IME learning options
- Character set options

For more information about these settings, see [Microsoft Traditional Chinese IME](https://support.microsoft.com/en-us/windows/microsoft-traditional-chinese-ime-ef596ca5-aff7-4272-b34b-0ac7c2631a38#ID0EBBD=Microsoft_Bopomofo).

### Change character width

The Bopomofo IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

### Use the IME Pad for advanced writing options

To open the IME Pad, open the right/click menu and select **IME Pad**. It has three modes that you can select with the icons on the left side of the window:

- **Hand Writing (CH)**: You can draw a Traditional Chinese character in the left box and then select one of the recognized characters from the right box to insert it into your text.
- **Strokes (CH)**: You can select any available character to insert it into your text. You can sort the character list by the number of strokes used to write it.
- **Radical (CH)**: Works like the Strokes mode, but you first choose the radical (a part of the final character) based on the number of strokes used to write it. Then select how many strokes remain, and finally choose a character from the available options.
- **Symbols (CH)**: You can quickly enter symbols from various subsets such as punctuation or mathematical.

Finally, the IME Pad lets you use the Backspace, Delete, Enter, Esc, Spacebar, and arrow keys with your mouse or touchpad.

### Use the IME toolbar to access options

To open the IME toolbar, open the right-click menu and select **IME toolbar**. It gives you another way to access some of the options discussed in this article.

- You can switch the input mode.
- You can change between half-width and full-width characters.
- You can open the [IME Pad](#use-the-ime-pad-for-advanced-writing-options).
- You can open the **Microsoft Bopomofo** settings page.

## Example

The Traditional Chinese word for summer is 夏天. It consists of two characters.

### Type with the Quick IME

The character 夏 contains the radicals 一 and 水, while the character 天 contains the radicals 一 and 大. To type the word 夏天, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Microsoft Quick** IME from the system tray and change to Chinese input mode, if necessary, then either:

- Enter 一水, then enter 5 to select the character 夏. Enter Shift + 2 to add the character 天.
- Enter 一水, then enter 5 to select the character 夏. Enter 一大, then enter 1 to select the character 天.

On an English keyboard, the radical 一 is entered using the m key, the radical 水 is entered using the e key, and the radical 大 is entered using the k key.

### Type with the Bopomofo IME

To type the word, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Microsoft Bopomofo** IME from the system tray and change to Chinese input mode, if necessary.

Using Bopomofo, the word for summer is entered with the following seven symbols: ㄒㄧㄚˋ ㄊㄧㄢ

On an English keyboard, the symbols are on the V, U, 8, 4, W, U, and 0 keys. After you type the first four symbols, you see they change to form a character, but it’s not the right character. Type the last three symbols and press the Spacebar. The second character is formed, and you see the first character changes to form the completed word.
