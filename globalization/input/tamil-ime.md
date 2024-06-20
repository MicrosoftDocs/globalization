---
title: Tamil IME
description: Installing and using the Tamil Input Method Editor (IME)
author: m-kauppinen
ms.author: v-mikau
ms.topic: how-to
ms.date: 06/19/2024
---

# Tamil IME

If you need to enter some text in Tamil, Windows includes an Input Method Editor and keyboard layouts that let you enter text using the Tamil script while using a typical keyboard with 101-105 keys. Using the IME doesn't require changing your current Windows display language.

## Add support for Tamil input

To add support for Tamil input to Windows:

1. Open Settings and select **Time & language** > **Language & region**.
1. Select **Add a language**. Select **Tamil** from the list and select **Next**.
1. Consider if you need any of the **Optional language features**. If you want to enter Tamil text while keeping your current Windows display language, none of them are necessary. When you're happy with your choices, select **Install**.

By default, Tamil is installed with the [Tamil 99](../keyboards/kbdtam99.md) keyboard. To install the Tamil Phonetic IME:

1. On the **Language & region** page, select the Options (**…**) icon next to **Tamil** and select **Language options**.
1. Select **Add a keyboard** and select **Tamil Phonetic**.

## Type Tamil text

The Windows system tray shows which keyboard layout is currently active, for example, **ENG**. You can switch between installed layouts (layouts in the **Preferred languages** list in Settings) by selecting the Windows logo key + Spacebar.

If you prefer, you can also change the layout by selecting the system tray icon and selecting the layout from the list. This method can be faster if you have more than two languages installed.

:::image type="content" source="images/keyboard-layouts.png" alt-text="Windows 11 with several keyboard layouts installed.":::

If multiple IME/keyboards are installed for a given language, the list and the tray icon will show a combination of language and layout.

### Use the Tamil Phonetic IME

To type text in the Tamil script using the Tamil Phonetic IME:

1. Select **Tamil Phonetic**. The system tray now shows **த** instead of **ENG** indicating that you can now type in Tamil.
1. Type the transliteration of the word you want with the English keys. As you type, notice that the Tamil Phonetic IME automatically converts the English letters into Tamil script suggestions. When you're finished typing, select Enter to convert your text into the first suggested Tamil word. You can also use the cursor keys to select a different suggestion.

### Use the Tamil 99 keyboard

To type text using the Tamil 99 keyboard:

1. Select **Tamil 99**. The system tray now shows **த** instead of **ENG** indicating that you can now type using the Tamil script.
1. Using the [Tamil 99](../keyboards/kbdtam99.md) keyboard layout, type the Tamil word you want.

## Example

The Tamil word for garden is தோட்டம், which can be transliterated as thottam.

### Type with the Tamil Phonetic IME

To type தோட்டம், select the Tamil Phonetic IME from the system tray. Then type *thottam* with the English keys. As you type, you can see how the IME turns the text into word suggestions. When you're finished typing, the top suggestion is the correct Tamil word. Select Enter to convert the English letters into Tamil script.

### Type with the Tamil 99 keyboard

To type தோட்டம், select the Tamil 99 keyboard layout from the system tray. Use the following keystrokes to type the Tamil word for garden:

| Tamil letter | Keystroke on the English US keyboard | Phonetic equivalent |
|--------------|--------------------------------------|---------------------|
| த | l | ta |
| ◌ோ | x | {vowel sign oo} |
| ட | o | tta |
| ◌் | f | {virama - isolates the consonant from tta}  |
| ட | o | tta |
| ம | k | ma |
| ◌் | f | {virama - isolates the consonant from tta}  |

When you're finished typing, select Spacebar or Enter. த and ோ will resolve to தோ and the word தோட்டம் appears on the screen.
