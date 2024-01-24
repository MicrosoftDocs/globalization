---
title: Use emoji to add context and emotion to your text-based messages
description: Understand the importance of considering cultural context when localizing emojis to ensure the intended meaning is conveyed accurately.
ms.date: 1/24/2024
author: jowilco
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-seo-date:10/31/2023
  - ai-gen-desc
---

# Emoji

Emoji are pictorial symbols (pictographs) that represent objects such as faces, places, weather, and animals. They're typically used with or as a replacement for text to add context via emotions.

While earlier versions of the Unicode standard included pictographic symbols, [Unicode 6.0](https://www.unicode.org/versions/Unicode6.0.0/), released in October 2010 specified a set of 722 emoji. Subsequent Unicode versions continue to expand the number of emoji defined by the standard.

To display glyphs defined in the Unicode standard in your UI, the font that you use needs to support the glyphs that you're using. Similarly, to display emoji, the device, browser, or font used must be able to represent the emoji.

Emoji can be convenient when conveying gestures, facial expressions, and other nonverbal elements of communication in text-based messages. However, like nonverbal communication, these cues and meanings vary by context. Context could include the sender’s and the recipient’s language, culture, and social group. In other words, when localizing emoji, you need to be especially careful that the intended meaning is conveyed correctly and appropriately for the target audience.

[Unicode 8.0](https://www.unicode.org/versions/Unicode8.0.0/), released in June 2015 added skin tone modifier characters to the emoji standard. These characters allow users to specify the skin tone of the emoji character that immediately precedes them.

## Emoji and variation selection

Like applying variation sequences to characters  to change the appearance when rendered, you can use variation sequences to change the appearance of emoji.

The Unicode Standard defines emoji variation sequences  that can be used. In the following sections, the display of the examples is dependent on the browser and the operating system.

### Emoji text and presentation sequences

You can choose to display emoji with a text presentation (similar in appearance to a dingbat font) or with an emoji presentation by using VS15 (U+FE0E) or VS 16 (U+FE0F) respectively.

<iframe src="text_emoji_presentation.html" height="80"></iframe>

### Emoji modifiers

You can change the appearance of emoji by using emoji modifiers. Here's an example showing the default BABY (U+1F476) emoji and the same emoji followed by an EMOJI MODIFIER FITZPATRICK (U+1F3FB..U+1F3FF) modifier.

<iframe src="char1F476_variation.html" height="100"></iframe>

### Emoji flag sequences

You can use sequences of Regional Indicator characters (U+1F1E6.. U+1F1FF) to display emoji country/region flags. In the following example:

- REGIONAL INDICATOR SYMBOL LETTER U (U+1F1FA) followed by REGIONAL INDICATOR SYMBOL LETTER S (U+ 1F1F8) can be combined to display the US flag.
- REGIONAL INDICATOR SYMBOL LETTER C (U+ 1F1E8) followed by REGIONAL INDICATOR SYMBOL LETTER A (U+ 1F1E6) can be combined to display the US flag.

<iframe src="flag_emoji.html" height="120"></iframe>

> [!TIP]
> Whether the flags are displayed is dependent on the browser, operating system, and font.
> 
> - The first line in the example shows the default browser/operating system/font behavior. This line might be rendered as letters (for example, Windows with Chromium browsers such as Edge or Chrome), or it might be rendered as flags.
> - The second line is using the Noto Color Emoji  font, which should be rendered as flags on Windows with Chromium browsers).

## Emoji ZWJ Sequences

You can use ZERO WIDTH JOINER (ZWJ) (U+200D) to create sequences of emoji  that render as a single emoji. This example shows two pairs of ADULT (U+1F9D1) and CHILD (U+1F9D2), with the second pair separated with ZERO WIDTH JOINER (U+200D).

<iframe src="zwj_sequence.html" height="80"></iframe>

## Inserting emojis using Windows

1. Type Windows logo key :::image type="icon" source="images/windows-logo-key.png" border="false":::  + . (period). The emoji keyboard appears.
1. Select an emoji with the mouse or keep typing to search through the available emojis for one you like.
1. If you're using Windows 11, you can express yourself with GIFs or Kaomoji (emoticons), or you can insert symbols from the same emoji panel.
