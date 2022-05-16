---
title: Japanese Localization Style Guide
description: Are you helping with translation into Czech, but don't have time to study all aspects of the Japanese Style Guide? Here are the ten most important aspects.
ms.date: 04/24/2019
---

# Top 10 Tips for Microsoft Translation into Japanese

Are you helping with translation into Japanese, but don't have time to study all aspects of the [full Japanese Style Guide](https://www.microsoft.com/ja-jp/language/StyleGuides)? Here are 10 of the most important aspects to keep in mind.

## 1. Keep the audience in mind

Microsoft products target a broad set of users, from technology enthusiasts and professionals to consumers. Remember who you are talking to, and adjust your text to be at the right technical level.

## 2. Stay true to the structure and intent of the source

Try to reflect the same grammatical structures as the source text. Consider the intent of the text, and convey the message precisely.

## 3. Be flexible

Flexibility and creativity may be required in some cases. Ensure that the translation sounds natural and appropriate for Japanese culture.

## 4. Pick the right term

The translation of key terminology can vary, depending on areas, contexts, and even which Microsoft product is being localized. Consult the appropriate glossaries and websites, such as:

- [Microsoft Language Portal](https://www.microsoft.com/ja-jp/language/) (terminology search)
- [Microsoft products](https://www.microsoft.com/ja-jp/) websites
- Third-party websites

## 5. Be aware of expressions and tone

Check that the translations are:

- Simple and crisp.
- Clear and precise.
- Grammatically correct.
- Polite, but not too formal. Don't use honorific and humble expressions (:::no-loc text="尊敬語":::, :::no-loc text="謙譲語":::).
- Friendly, but professional.
- Free of jargon.
- Not offensive to any group or person.
- Verified for geopolitical accuracy, such as country or region names.

## 6. Understand basic writing styles

Use polite (:::no-loc text="です・ます":::) style for descriptive sentences in general. Plain style (:::no-loc text="だ・である":::) and noun phrases are appropriate when short and simple texts are preferred. To learn more, see the "Style and tone consideration" section in the [Japanese Style Guide](https://www.microsoft.com/ja-jp/language/StyleGuides).

Example:

- Use polite style in error messages and body text.
- Use plain style/noun phrases for list items, buttons, titles, and headings.

## 7. Enclose UI labels

Add brackets ([ ]) to refer to a UI item with a label. To learn more, see the "User interface" section in the [Japanese Style Guide](https://www.microsoft.com/ja-jp/language/StyleGuides).

Example:

_English_: Select Cancel.

_Our style_: :::no-loc text="[キャンセル] を選びます。":::

_Not our style_: :::no-loc text="キャンセルを選びます。":::

## 8. Pay attention to katakana compound words and prolonged sound mark

Insert spaces to katakana compounds where they appear in the English words. To learn more, see the "Compounds" section in the [Japanese Style Guide](https://www.microsoft.com/ja-jp/language/StyleGuides). For general spacing rules, see the "Symbols & spaces" section in the guide.

Example:

_English_: error message

_Our style_: :::no-loc text="エラー メッセージ":::

_Not our style_: :::no-loc text="エラーメッセージ":::

The prolonged sound mark should be added to a katakana word when:

- A source English term has the suffix -ar, -er, or -or.
- The katakana word has fewer than four characters, including the prolonged mark and excluding small characters such as :::no-loc text="促音"::: and :::no-loc text="拗音"::: (:::no-loc text="ッ, ャ, ュ, ョ, ァ, ィ, ゥ":::).

Example:

_English_: computer

_Our style_: :::no-loc text="コンピューター":::

_Not our style_: :::no-loc text="コンピュータ":::

Example:

_English_: procedure

_Our style_: :::no-loc text="プロシージャ":::

_Not our style_: :::no-loc text="プロシージャ―":::

To learn more about the rules and exceptions, see the "Katakana prolonged sound mark" section in the [Japanese Style Guide](https://www.microsoft.com/ja-jp/language/StyleGuides).

## 9. Know what to leave in English

Items that aren't usually translated include:

- Product names.
- Trademarks.
- Acronyms.
- Placeholders (for example, {1} and %s).
- Escape characters (for example, \n and \r, which can be displayed as "￥n").
- Registry keys.
- Codes.
- Variables.
- Copyright information: "&copy; 2019 Microsoft Corporation. All rights reserved."
- References to UI labels from unlocalized products. Add a tentative translation in parentheses. See the example below.

Example:

_English_: The Add/Delete dialog box appears.
_Our style_: [Add/Delete] :::no-loc text="(追加/削除) ダイアログ ボックスが表示されます。":::

## 10. Use the right reference material

There is more, of course. If you are in doubt, consult the terminology, translation, [full Japanese Style Guide](https://www.microsoft.com/ja-jp/language/StyleGuides) and the following references:

- :::no-loc text="平成 3 年 6 月 28 日 内閣告示第 2 号「外来語の表記」":::
- :::no-loc text="昭和 61 年 7 月 1 日 内閣告示第 1 号「現代仮名遣い」":::
- :::no-loc text="平成 22年 11 月 30 日 内閣告示第 2 号「常用漢字表」":::
- :::no-loc text="昭和 48 年 6 月 18 日 内閣告示第 2 号「送り仮名の付け方」":::
- :::no-loc text="『新しい国語表記ハンドブック』（三省堂）":::
- :::no-loc text="『用字用語 新表記辞典』（第一法規）":::
