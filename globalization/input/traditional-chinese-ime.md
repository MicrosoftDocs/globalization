---
title: Traditional Chinese IME
description: Installing and using the Traditional Chinese Input Method Editor (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Traditional Chinese IME

If you need to enter some text in Traditional Chinese, Windows includes several Input Method Editors (IMEs) to let you enter text using Traditional Chinese characters while using a typical keyboard with 101-105 keys. Using the IME doesn't require changing your current Windows display language.

This article discusses the following IMEs:

- Chinese Traditional Array: Chinese Traditional Array is a shape-based input method that enables you to use the structure of characters to input text. Each Traditional Chinese character can be decomposed to one or more elements or radicals. The Chinese Traditional Array IME allows users to use keystrokes that correspond to the decomposed elements to build up a final character.
- Chinese Traditional DaYi: DaYi is a shape-based input method that enables users to use the shape of characters to input text. Each Traditional Chinese character can be decomposed to one or more elements or radicals. The DaYi IME allows users to use keystrokes that correspond to the decomposed elements to build up a final character. DaYi uses stroke order to organize the decomposed characters, rather than geometric shape that is used in ChangJie.
- Microsoft Bopomofo: Bopomofo (also known as Zhuyin) is a phonetic system. Users type the phonemes of the Chinese character.
- Microsoft ChangJie: ChangJie (or Cangjie) or  is a shape-based input method that enables users to use the shape of characters to input text. Each Traditional Chinese character can be decomposed to one or more elements or radicals. The ChangJie IME allows users to use keystrokes that correspond to the decomposed elements to build up a final character. ChangJie uses geometric shape to organize the decomposed characters, rather than stroke order that is used in DaYi.
- Microsoft Quick: Quick is also known as Simplified ChangJie. It lets users enter a character’s first and the last stroke used in the full ChangJie system and then pick a character from the conversion candidate window.

## Add support for Traditional Chinese input

To add support for Traditional Chinese input to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Chinese (Traditional, Hong Kong SAR)** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. If you want to enter Traditional Chinese text while keeping English as your Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

By default, Traditional Chinese support is installed with the Microsoft Quick IME. To any of the other IMEs:

1. On the **Language & region** page, select the Options (**…**) icon next to **Chinese (Traditional, Hong Kong SAR)** and select **Language options**.
1. Select **Add a keyboard** and select the IME that you want to install.

## Type Traditional Chinese text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (layouts in the **Preferred languages** list in Settings) by selecting the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

## Use the Chinese Traditional Array IME

To type text using Traditional Chinese with the Chinese Traditional Array IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Chinese Traditional Array** IME. The system tray now shows **行** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), use the Shift key or select the input mode icon.
1. Type the Traditional Chinese character or word using keystrokes corresponding to the decomposed character. As you enter the keystrokes, a conversion candidate window appears.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Number keys to quickly select the corresponding candidate
    - Shift + number key to choose a candidate
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To move to the next/previous candidate, use the Down and Up arrow keys. To select one of these candidates, use the Shift key + the corresponding number.

## Use the Chinese Traditional DaYi IME

To type text using Traditional Chinese with the Chinese Traditional DaYi IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Chinese Traditional DaYi** IME. The system tray now shows **易** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), use the Shift key or select the input mode icon.
1. Type the Traditional Chinese character or word using keystrokes corresponding to the decomposed character. As you enter the keystrokes, a conversion candidate window appears.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Number keys to quickly select the corresponding candidate
    - Shift + number key to choose a candidate
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To move to the next/previous candidate, use the Down and Up arrow keys.. To select one of these candidates, use the Shift key + the corresponding number.

## Use the Bopomofo IME

To type text using Traditional Chinese with the Bopomofo IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Microsoft Bopomofo** IME. The system tray now shows **ㄅ** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), use the Shift key or select the input mode icon.
1. Type the Traditional Chinese character or word using the phonetic Bopomofo symbols. After you type the symbols for the word, use the Down arrow key to open the conversion candidate window. It shows matches for what you typed.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Enter to select the currently focused candidate
    - Number keys to quickly select the corresponding candidate
    - Spacebar to move to the next page
    - Tab key to expand the list to a table that you can navigate with the arrow keys
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To select one of these candidates, use the Shift key + the corresponding number. If there's more than one page of suggestions, use the Spacebar to move to the next page.

> [!NOTE]
> You You need to switch on the **Prompt associated phrases of the input characters** setting to be able to use the associate phrase window. For instructions, see [Use the Bopomofo IME right-click menu for additional options](#use-the-bopomofo-ime-right-click-menu-for-additional-options).

### Use the Bopomofo IME right-click menu for additional options

When the Traditional Chinese keyboard layout is active, you can right-click the input mode icon (**中** or **英**) to access various options. The right-click menu also has a shortcut to **Microsoft Bopomofo** IME settings. You can change the following settings related to using the IME:

- Default input mode and other input settings
- Input assistance options, such as the use of the associate phrase window
- Keyboard shortcuts
- IME learning options
- Character set options

For more information about these settings, see [Microsoft Traditional Chinese IME](https://support.microsoft.com/en-us/windows/microsoft-traditional-chinese-ime-ef596ca5-aff7-4272-b34b-0ac7c2631a38#ID0EBBD=Microsoft_Bopomofo).

### Change character width with the Bopomofo IME

The Bopomofo IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

### Use the IME Pad for advanced writing options

To open the IME Pad, open the right-click menu and select **IME Pad**. It has three modes that you can select with the icons on the left side of the window:

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

## Use the ChangJie IME

To type text using Traditional Chinese with the ChangJie IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Microsoft ChangJie** IME. The system tray now shows **倉** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), use the Shift key or select the input mode icon.
1. Select the keys that correspond to the decomposed elements of the Traditional Chinese character. Select the Spacebar. If there's a single character that corresponds to the keystrokes, that character is inserted. Otherwise, the conversion candidate window opens to show matches for what you typed.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Enter to select the currently focused candidate
    - Number keys to quickly select the corresponding candidate
    - Spacebar to move to the next page
    - Tab key to expand the list to a table that you can navigate with the arrow keys
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To select one of the candidates, use the Shift key + the corresponding number. If there's more than one page of suggestions, select the Spacebar to move to the next page.

> [!NOTE]
> You need to switch on the **Prompt associated phrases of the input characters** setting to be able to use the associate phrase window. For instructions, see [Use the ChangJie IME right-click menu for additional options](#use-the-changjie-ime-right-click-menu-for-additional-options).

### Use the ChangJie IME right-click menu for additional options

When the Traditional Chinese keyboard layout is active, you can right-click the input mode icon (中 or 英) to access various options. The right-click menu also has a shortcut to **Microsoft ChangJie** IME settings. You can change the following settings related to using the IME:

- Default input mode and other input settings
- Input assistance options, such as the use of the associate phrase window
- Character set options

### Change character width with the ChangJie IME

The ChangJie IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

## Use the Quick IME

To type text using Traditional Chinese with the Quick IME:

1. Select **Chinese (Traditional, Hong Kong SAR)** with the **Microsoft Quick** IME. The system tray now shows **速** instead of **ENG**, and a new icon showing **中** (indicating Chinese input mode) appears next to it. To change between Chinese and English input (indicated by **英**), use the Shift key or select the input mode icon.
1. Select the two keys that correspond to the first and the last ChangJie elements of the Traditional Chinese character. The conversion candidate window opens and shows matches for what you typed.
1. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Enter to select the currently focused candidate
    - Number keys to quickly select the corresponding candidate
    - Spacebar to move to the next page
    - Tab key to expand the list to a table that you can navigate with the arrow keys
    - Esc to close the window without making a selection and deleting the character you entered
1. After you select a character, the associate phrase window might offer text candidates related to what you typed. To select one of the candidates, use the Shift key + the corresponding number. If there's more than one page of suggestions, select the Spacebar to move to the next page.

> [!NOTE]
> You need to switch on the **Prompt associated phrases of the input characters** setting to be able to use the associate phrase window. For instructions, see [Use the Quick IME right-click menu for additional options](#use-the-quick-ime-right-click-menu-for-additional-options).

### Use the Quick IME right-click menu for additional options

When the Traditional Chinese keyboard layout is active, you can right-click the input mode icon (中 or 英) to access various options. The right-click menu also has a shortcut to **Microsoft Quick** IME settings. You can change the following settings related to using the IME:

- Default input mode and other input settings
- Input assistance options, such as the use of the associate phrase window
- Character set options

### Change character width with the Quick IME

The Quick IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

## Example

The Traditional Chinese word for summer is 夏天. It consists of two characters.

### Type with the Chinese Traditional Array IME

To type 夏天, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Chinese Traditional Array** IME from the system tray and change to Chinese input mode, if necessary.

The character 夏 can be decomposed to 一, 丿, 目, and 夂. These elements correspond to the keys A, L, J, and . on the US keyboard. The character 天 contains the radicals 一 and 大. These elements correspond to the keys A and Z on the US keyboard. To type 夏天, you can either:

- Enter "ALJ." then use the Shift key and the appropriate number to select the character 夏. Continue by typing "AZ" then use the Shift key and the appropriate number to select the character 天.
- Enter "ALJ." then use the Shift key and the appropriate number to select the character 夏. The candidate window remains open, allowing you to use the Shift key and the appropriate number to select the character 天.

### Type with the Chinese Traditional DaYi IME

To type 夏天, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Chinese Traditional DaYi** IME from the system tray and change to Chinese input mode, if necessary.

The character 夏 can be decomposed to 丆, 目, and 夂. These elements correspond to the keys H, 3, and X on the US keyboard. The character 天 contains the radicals 一 and 大. These elements correspond to the keys E and V on the US keyboard. To type 夏天, you can either:

- Enter "H3X" then select the Spacebar to generate the character 夏. Continue by typing "EV" then select the Spacebar to generate the character 天.
- Enter "H3X" then select the Spacebar to generate the character 夏. The candidate window remains open, allowing you to use the Shift key and the appropriate number to select the character 天.

### Type with the Bopomofo IME

To type 夏天, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Microsoft Bopomofo** IME from the system tray and change to Chinese input mode, if necessary.

The word for summer is entered with the following seven symbols: ㄒㄧㄚˋ ㄊㄧㄢ

On an English keyboard, the symbols are on the V, U, 8, 4, W, U, and 0 keys. After you type the first four symbols, you see they change to form a character, but it’s not the right character. Type the last three symbols and select the Spacebar. The second character is formed, and you see the first character changes to form the completed word.

### Type with the ChangJie IME

The character 夏 is decomposed to the radicals 一, 山, 竹, and 水, while the character 天 can be decomposed to 一 and 大. On an English keyboard:

- the radical 一 is entered using the m key
- the radical 山 is entered using the u key
- the radical 竹 is entered using the h key
- the radical 水 is entered using the e key
- the radical 大 is entered using the k key.

To type 夏天, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Microsoft ChangJie** IME from the system tray and change to Chinese input mode, if necessary, then either:

- Enter "MUHE" then select the Spacebar to generate the character 夏. Enter Shift + 1 to add the character 天.
- Enter "MUHE" then select the Spacebar to generate the character 夏. Enter "MK" then select the Spacebar to generate the character 天.

### Type with the Quick IME

The character 夏 starts with the radical 一 and ends with the radical 水, while the character 天 can be decomposed to 一 and 大. On an English keyboard, the radical 一 is entered using the m key, the radical 水 is entered using the e key, and the radical 大 is entered using the k key.

To type 夏天, select the **Chinese (Traditional, Hong Kong SAR)** keyboard layout with the **Microsoft Quick** IME from the system tray and change to Chinese input mode, if necessary, then either:

- Enter "ME" then enter the appropriate number to select the character 夏. Enter Shift + 2 to add the character 天.
- Enter "ME" then enter the appropriate number to select the character 夏. Enter "MK" then enter 1 to select the character 天.
