---
title: Malayalam IME
description: Installing and using the Malayalam Input Method Editor (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: how-to
ms.date: 06/19/2024
---

# Malayalam IME

If you need to enter some text in Malayalam, Windows includes an Input Method Editor and keyboard layouts that let you enter text using the Malayalam script while using a typical keyboard with 101-105 keys. Using the IME doesn't require changing your current Windows display language.

## Add support for Malayalam input

To add support for Malayalam input to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Malayalam** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. If you want to enter Malayalam text while keeping your current Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

By default, Malayalam is installed with the [Malayalam INSCRIPT](../keyboards/kbdinmal.md) keyboard. To install the Malayalam Phonetic IME:

1. On the **Language & region** page, select the Options (**…**) icon next to **Malayalam** and select **Language options**.
1. Select **Add a keyboard** and select **Malayalam Phonetic**.

## Type Malayalam text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (layouts in the **Preferred languages** list in Settings) by selecting the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

If multiple IME/keyboards are installed for a given language, the list and the tray icon will show a combination of language and layout.

### Use the Malayalam Phonetic IME

To type text in the Malayalam script using the Malayalam Phonetic IME:

1. Select **Malayalam Phonetic**. The system tray now shows **മല** instead of **ENG** indicating that you can now type in Malayalam.
1. Type the transliteration of the word you want with the English keys. As you type, notice that the Malayalam Phonetic IME automatically converts the English letters into Malayalam script suggestions. When you're finished typing, select Enter to convert your text into the first suggested Malayalam word. You can also use the cursor keys to select a different suggestion.

### Use the Malayalam INSCRIPT keyboard

To type text using the Malayalam INSCRIPT keyboard:

1. Select **Malayalam INSCRIPT**. The system tray now shows **മല** instead of **ENG** indicating that you can now type using the Malayalam script.
1. Using the [Malayalam INSCRIPT](../keyboards/kbdinmal.md) keyboard layout, type the Malayalam word you want.

## Example

The Malayalam word for garden is തോട്ടം, which can be transliterated as theaattam or thottam.

### Type with the Malayalam Phonetic IME

To type തോട്ടം, select the Malayalam Phonetic IME from the system tray. Then type *thottam* with the English keys. As you type, you can see how the IME turns the text into word suggestions. When you're finished typing, the top suggestion is the correct Malayalam word. Select Enter to convert the English letters into Malayalam script.

### Type with the Malayalam INSCRIPT keyboard

To type തോട്ടം, select the Malayalam INSCRIPT keyboard layout from the system tray. Use the following keystrokes to type the Malayalam word for garden:

| Malayalam letter | Keystroke on the English US keyboard | Phonetic equivalent |
|----------------|--------------------------------------|---------------------|
| ത | l | ta |
| ◌ോ | a | {vowel sign oo} |
| ട | ' | tta |
| ◌് | d | {virama - isolates the consonant from tta}  |
| ട | ' | tta |
| ◌ം | x | {anusvara - nasal sound} |

When you're finished typing, the word തോട്ടം appears on the screen.
