---
title: Japanese IME
description: Installing and using the Japanese Input Method Editor (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 02/15/2024
---

# Japanese IME

If you need to enter some text in Japanese, the Japanese Input Method Editor (IME) for Windows lets you enter text using hiragana or katakana characters while using a typical keyboard with 101-105 keys and keeping English as your Windows display language. The IME also converts your input into kanji characters.

## Add the Japanese keyboard layout

To add the Japanese keyboard layout to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Japanese** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. For entering Japanese text while keeping English as your Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

## Type Japanese text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (those in the **Preferred languages** list in Settings) by pressing the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

To type text using Japanese characters, do the following:

1. Select **Japanese Microsoft IME**. The system tray now shows a **Ⓙ** icon instead of **ENG**, and a new icon showing **A** (indicating English input mode, also known as half-width alphanumeric) appears next to it.
1. Select the **A** icon. The input mode changes to **あ** indicating that you can now type Japanese hiragana characters. You can also change between Japanese and English input by pressing the Alt key + Back quote (`).
1. Start typing the Japanese character or word using its phonetic transcription. The conversion candidate window opens and shows matches for what you typed. You can keep typing and the candidate window updates in real time. Press the Spacebar to convert your current input into kanji. See the [example](#example) at the end of this article.
1. To move the focus to the candidate window, press the Tab key. To navigate the window, use your mouse or the following keys:
    - Down and Up arrow keys to move to the next/previous candidate
    - Tab key to expand the list to a table that you can navigate with the arrow
    - Number keys to quickly select the corresponding candidate
    - Enter to select the currently focused candidate
    - Esc to close the window without making a selection

## Keyboard shortcuts

The following table lists some useful keyboard shortcuts for the Japanese IME.

|To do this |Press this |
|-----------|-----------|
|Turn Japanese input on/off. |Alt + Back quote (`) |
|Use the hiragana key of a Japanese keyboard (106/109 key). |Ctrl + Caps lock |
|Use the Shift + hiragana key of a Japanese keyboard (106/109 key). |Alt + Caps lock |
|Use the Eisu (英数 - alphanumeric) key of a Japanese keyboard (106/109 key). |Shift + Caps lock |
|Remove the selected candidate from the prediction candidate window. |Ctrl + Delete |
|Search for the selected candidate in the prediction candidate window. |Ctrl + B |
|Expand/collapse the table view in the conversion candidate window. |Tab key |
|Open Emoji picker. |Windows logo key + period (.) |
|Turn IME private mode on/off. |Ctrl + Shift + F10 |
|Convert input string to hiragana. |F6 |
|Convert input string to full-width katakana. |F7 |
|Convert input string to half-width katakana. |F8 |
|Convert input string to full-width alphanumeric. |F9 |
|Convert input string to half-width alphanumeric. |F10 |

## Use the right-click menu for additional options

When the Japanese keyboard layout is active, you can right-click the input mode icon to access additional options and tools. The right-click menu also has a shortcut to **Microsoft IME** settings. You can change the following settings related to using the IME:

- Input settings such as punctuation
- Character type and set conversion candidate settings
- Predictive input settings
- Keyboard and touch-related settings
- IME learning and dictionary settings
- IME appearance settings
- Usage data collection settings

For more information about these settings, see [Microsoft Japanese IME](https://support.microsoft.com/en-us/windows/microsoft-japanese-ime-da40471d-6b91-4042-ae8b-713a96476916#ID0EBBL=English_keyboard_(101/102_key)).

### Change character width and input mode

The Japanese IME allows typing with both half-width and full-width characters. To change the width and input mode, open the right-click menu and select from the following options:

- **Hiragana**
- **Full-width Katakana**
- **Full-width Alphanumeric**
- **Half-width Katakana**
- **Half-width Alphanumeric**

### Use the IME Pad for advanced writing options

To open the IME Pad, open the right-click menu and select **IME Pad**. It has three modes that you can select with the icons on the left side of the window:

- **Hand Writing (JA)**: You can draw a Japanese character in the left box and then select one of the recognized characters from the right box to insert it into your text.
- **Character List (JA)**: You can select any font installed on the computer, view every character available with that font, and select them for insertion into your text.
- **Soft Keyboard (JA)**: You can enter alphanumeric characters, hiragana, and katakana with an on-screen keyboard that resembles the Windows On-Screen Keyboard (OSK).
- **Strokes (CH)**: You can select any available character to insert it into your text. You can sort the character list by the number of strokes used to write it.
- **Radical (CH)**: Works like the Strokes mode, but you first choose the radical (a part of the final character) based on the number of strokes used to write it, and then choose a character or syllable that includes the selected radical.

Finally, the IME Pad lets you use the Backspace, Delete, Enter, Esc, Spacebar, Convert, and arrow keys with your mouse or touchpad.

### Use the IME toolbar to access options

To open the IME toolbar, open the right-click menu and select **IME toolbar**. It gives you another way to access some of the options discussed in this article.

- You can [change character width and input mode](#change-character-width-and-input-mode).
- You can open the [IME Pad](#use-the-ime-pad-for-advanced-writing-options).
- You can open the user dictionary or add-on dictionary.
- You can switch between kana and romaji input.
- You can open the Microsoft Japanese IME settings page.

## Example

The Japanese word for summer is 夏 which is a single kanji character. Its phonetic romanization is "natsu."

To type the word, select the Japanese keyboard layout from the system tray and change to Japanese hiragana input mode, if necessary. Then type "natsu" without any spaces. You see that the Japanese IME turns your input into hiragana syllables: なつ

The candidate window also opens and shows a list of matches. But all you need to finish the character and convert it into kanji is to press the Spacebar once. If you press Enter, the Japanese IME keeps the word in hiragana.
