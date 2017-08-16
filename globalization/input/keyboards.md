---
title: Keyboards, Other Input Methods, and Text Predication
description: 
ms.assetid: b7be46c4-99d5-41f0-9902-b26cabc1d2bf
ms.date: 04/21/2017
---
# Keyboards, Other Input Methods, and Text Predication

If you are using a standard control, you should have no need to worry about the user’s input method. This will be handled for you automatically. Advanced applications (such as a text editor) that need to have full control over how input languages are handled should monitor—and should be able to respond to—the user’s changes.

You will find [keyboard input documentation on MSDN](https://msdn.microsoft.com/en-us/library/ms646268(VS.85).aspx).

The exception may be for keyboard shortcuts. If you define a shortcut as Alt-S and there is no S on the keyboard, what does that mean for the user?

![Hindi Traditional Keyboard](/media/hubs/globalization/IC866727.png "Hindi Traditional Keyboard")
[**Figure: Hindi Traditional Keyboard** ]{}

## Enable Input Method Editors (IMEs) and Text Prediction

For some languages, the number of characters needed for writing the language is greater than the number of keys on a standard keyboard (e.g., Chinese). For others, the complexity of the writing system itself means that a model of one key equating one character will not work well (e.g., Malayalam). To allow users to write in such languages, Input Method Editor (IME) applets have been created for each language. These are provided by the platform or available through third-party vendors. In some cases, multiple IMEs may exist for the same language.

For languages with extremely large character sets, the IME presents a candidate window based on the text entry. The candidates usually have a one-to-many relationship to the text typed. There are two basic models within this category. The first is used for languages such as Japanese where there exist defined phonetic systems ([hiragana](https://en.wikipedia.org/wiki/Hiragana) and [katakana](https://en.wikipedia.org/wiki/Katakana)) that can be used to write most words. The conversion is from this phonetic forms to the more formal [kanji](https://en.wikipedia.org/wiki/Kanji). The second is where there is not a phonetic system within the language so transliteration using the Latin script is used. An example of this is the [pīnyīn](https://en.wikipedia.org/wiki/Pinyin) system used for Chinese. (Technically, any simple writing system language could be used, but the Latin script is most common.) For both systems, the user enters text in a phonetic form and can then select the final character(s) they want. That input is converted to a list of potential candidates for the final characters and the user selects the desired text. Once the final characters are selected, that text is input into the text stream.

IMEs are also relevant for improved text entry (particularly on touch devices, such as mobile phones). The IME logic is what allows for text prediction, even for languages with a simple character-to-key model. The candidate list is based on prediction rather than phonetics and is not required to input text into the text stream. The IME model is also what underlies the press-and-hold experience that allows a single key on a touch keyboard to have numerous alternate characters.

When implementing IME support, the developer should consider the following:

-   The string composition, candidate selection, and input all occur at the input position.
-   The number of key events will likely not equal the number of characters displayed.
-   For fields, such as passwords, it is recommended that the IME candidate model not be used as it makes observing the password easier and, perhaps more critically, the representation of the password length is ambiguous.
-   What happens when the program receives events while text is in undetermined state?
-   What happens when the user triggers a short cut associated with IME (e.g., hits ESC)?
-   Maximum character limits (whether byte based or visually based) are more complex with IME input. A common problem case for this is entering text in fields with character length limits – does the limit apply to the text as entered or text as displayed? For complex writing systems, the number of key events may be greater than the final candidate length. For text prediction, the user might select a predicted word that exceeds the limit.


