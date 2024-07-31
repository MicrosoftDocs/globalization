---
title: Korean IME
description: Installing and using the Korean Input Method Editors (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: how-to
ms.date: 06/19/2024
---

# Korean IME

If you need to enter some text in Korean, the Korean Input Method Editor and the Microsoft Old Hangul (IME) for Windows lets you enter text using the Korean Hangul writing system while using a typical keyboard with 101-105 keys. Using the IME doesn't require changing your current Windows display language.

## Add support for Korean input

To add support for Korean input to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Korean** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. If you want to enter Korean text while keeping your current Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

By default, Korean support is installed with the Microsoft IME which enables you to type Hangul and Hanja. You can also use the Microsoft Old Hangul IME which enables you to use jamo that are no longer in common use in modern Hangul. To install the Microsoft Old Hangul IME:

1. On the **Language & region** page, select the Options (**…**) icon next to **Korean** and select **Language options**.
1. Select **Add a keyboard** and select **Microsoft Old Hangul**.

## Type Korean text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (layouts in the **Preferred languages** list in Settings) by selecting the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

If multiple IME/keyboards are installed for a given language, the list and the tray icon will show a combination of language and layout.

To type text using Hangul:

1. Select **Korean Microsoft IME**. The system tray now shows **한** instead of **ENG**, and a new icon showing **A** (indicating English input mode) appears next to it.
1. Select the **A** icon. The input mode changes to **가** indicating that you can now type Hangul letters. You can also change between Korean and English input by selecting the right Alt key.
1. Type Korean consonants with your left hand and vowels with your right hand. The vowel ㅠ is located on the B key of the English keyboard and users who are familiar with the Korean keyboard typically type ㅠ with their right hand. Use the Shift key to type compound consonants (Shift + Q, W, E, R, and T) and compound vowels (Shift + O and P).

As you type, you notice that the Korean IME automatically arranges the Hangul letters into blocks representing syllables.

### Use the Windows On-Screen Keyboard (OSK) to learn

The Windows OSK is a convenient way to learn which Hangul letter is assigned to which English key, and you can also use it to enter text. To switch the OSK on or off, select the Windows logo key + Ctrl + O. For more information, see [Use the On-Screen Keyboard (OSK) to type](https://support.microsoft.com/en-us/windows/use-the-on-screen-keyboard-osk-to-type-ecbb5e08-5b4e-d8c8-f794-81dbf896267a).

## Use the right-click menu for additional options

When the Korean keyboard layout is active, you can right-click the input mode icon (**A** or **가**) to access additional options and tools. The right-click menu also has a shortcut to **Microsoft IME** settings.

### Change character width

The Korean IME allows typing with both half-width and full-width characters. To change the width, open the right-click menu and select **Character width** > **Half-width** or **Full-width**.

### Convert Hangul to Hanja characters

Hanja characters are Chinese characters used to write Korean. If you need to convert a Hangul word into Hanja:

1. Type the word with Hangul letters.
1. Open the right-click menu and select **Hanja Convert**. You can also select the right Ctrl key.
1. If there are several matching words, the Korean IME opens a list from which you can select the one you want.

### Use the IME Pad for advanced writing options

To open the IME Pad, open the right-click menu and select **IME Pad**. It has three modes that you can select with the icons on the left side of the window:

- **HandWriting (KO)**: You can draw a Korean character in the left box and then select one of the recognized characters from the right box to insert it into your text.
- **Strokes (KO)**: You can change to any installed Korean font and then select any available character or syllable to insert it into your text. You can sort the syllable list by the number of strokes used to write it.
- **Radical (KO)**: Works like the Strokes mode, but you first choose the radical (a part of the final character) based on the number of strokes used to write it, and then choose a character or syllable that includes the selected radical.

Finally, the IME Pad lets you use the Backspace, Delete, Enter, Esc, Spacebar, Hanja, and arrow keys with your mouse or touchpad.

## Example

The Korean word for summer is 여름. It consists of five letters: ㅇㅕㄹㅡㅁ

To type the word, select the Korean keyboard layout from the system tray and change to Korean input mode, if necessary. Then switch on the Windows OSK so you can easily find the five letters on your keyboard (they are on the O, U, F, M, and A keys). As you type them, you can see how the IME turns them into two syllabic blocks, changing the blocks as you type.

## Using the Microsoft Old Hangul IME for historical jamo

The Hunminjeongeum included 28 letters, but 4 of these letters (ㆆ, ㆁ, ㅿ, and ·) are no longer in common use in modern Hangul. Similarly, digraphs like ㅸ and ㅼ are no longer used. For example, 꿈 (kkum - "dream") was previously written as ᄭᅮᆷ. The Microsoft Old Hangul IME enables you to enter these jamo.

To type text using the Microsoft Old Hangul IME:

1. Select **Korean Microsoft Old Hangul**. The system tray now shows **옛** instead of **ENG**, and a new icon showing **A** (indicating English input mode) appears next to it.
1. Select the **A** icon. The input mode changes to **가** indicating that you can now type Hangul letters. You can also change between Korean and English input by selecting the right Alt key.
1. Type the jamo you want to use. For example, to type ᄭᅮᆷ, select ㅅ, ㄱ, ㅜ, and ㅁ. On the US English keyboard, these jamo are on the T, R, N, and A keys. The Microsoft Old Hangul IME automatically arranges the jamo into a block representing the syllable. Note that if you selected the same jamo on the standard Korean IME, it would form ㅅ굼 as the digraph ㅼ isn't recognized as modern Hangul.

When the Korean keyboard layout is active, you can right-click the input mode icon (**A** or **가**) to access additional options and tools. One of these tools is **Soft Keyboard** which shows the jamo on the screen and lets you select them with your mouse or touchpad.

:::image type="content" source="images/old-hangul.png" alt-text="The soft keyboard from the Microsoft Old Hangul IME, showing the placement of obsolete and modern jamo.":::
