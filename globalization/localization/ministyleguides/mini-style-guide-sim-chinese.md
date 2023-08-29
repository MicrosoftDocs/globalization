---
title: Simplfied Chinese Localization Style Guide
description: Are you helping with translation into Simplfied Chinese, but don't have time to study all of the Simplfied Chinese Style Guide? Here are the ten most important aspects.
ms.date: 06/24/2019
---

# Top 10 Tips for Microsoft Translation into Simplfied Chinese

Are you helping with translation into Simplfied Chinese, but don't have time to study all aspects of the [Simplfied Chinese Style Guide](../../reference/microsoft-style-guides.md)? Here are ten of the most important aspects to keep in mind.

## 1.    Check the provided reference materials

It is important to check the existing reference materials when you are working on Microsoft projects, especially when you have questions. See [Microsoft language resources](../../reference/microsoft-language-resources.md) for links to terminology resources, UI strings, and style guides. You might also receive instructions for a specific project.

## 2.    Keep the audience in mind

The purpose of any translation is to convey information to the audience, which is consistent with the Microsoft commitment to empowering people to achieve more. This means you should choose the right words for the audience and avoid clumsy, unnatural-sounding sentences and word-for-word translation. In a word, readability is the first priority. To achieve that readability, make sure that you understand the source text completely, and then rewrite just like you are writing the contents yourself.

Example:

_English_: The best of work and play.

_Our style_: :::no-loc text="尽善尽美的工作和娱乐体验。":::

_Not our style_: :::no-loc text="最棒的工作和娱乐。":::

## 3.    Keep the same style and voice as the source text

When translating into Simplified Chinese, write in a way that reflects the Microsoft voice, which means choosing words and grammatical structures that reflect the same style as the source text. The general style should be clear, friendly, and concise. Text that is written in the Microsoft voice reflects the short, simple words spoken in everyday conversations and avoids an unnecessarily formal tone.

Example:

_English_: Something bad happened! Unable to locate downloaded files to create your bootable USB flash drive.

_Our style_: :::no-loc text="发生错误! 找不到下载的文件，无法创建可启动的 U 盘。":::

_Not our style_: :::no-loc text="发生了糟糕的事情! 无法找到已经下载的文件来创建您的可启动的 USB闪存驱动器。":::

## 4.    Follow the language-specific standard

When you are translating, follow the Simplified Chinese standards for grammar, syntax, punctuation, and orthography. And also keep in mind some Microsoft preferences. In Simplified Chinese, there are two sets of conventions for the localization of software and documentation: half-width punctuation and full-width punctuation. For example, in software localization, use English parentheses ( ). In documentation localization, use double-byte parentheses（）if the text surrounded by the parentheses includes double-byte characters. If it doesn't, use single-byte parentheses ( ).

Refer to the full Style Guide for information about how to use punctuation correctly.

Example:

Example in software localization:

_English_: Add additional metadata (such as validation)

_Our style_: :::no-loc text="添加其他元数据 (如验证)。":::

Example:

Example in documentation localization:

_English_: The following features change when you open your Microsoft PowerPoint 2010 presentation in an earlier version of PowerPoint (installed). 

_Our style_: :::no-loc text="在早期版本的 PowerPoint（已安装）中打开 Microsoft PowerPoint 2010 演示文稿时，下列功能会发生变化。":::

## 5.    Be careful with elements that should not be translated

When working on Microsoft projects, be aware that some words should not be translated. Application and product names are often trademarked or may be trademarked in the future, so they are rarely translated. Occasionally, feature names are trademarked too. Trademarked names and the name Microsoft Corporation shouldn't be localized unless local laws require translation and an approved translated form of the trademark is available. Therefore, before translating these elements, first make sure that they are translatable. Verify that the term is not on the [list of Microsoft trademarks](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/default.aspx) before translating.

## 6.    Be consistent in your translation

For the best user experience, it is important to use consistent terminology, language style, and text formatting in the localized content. Translate all menus, menu items, commands, buttons, check boxes, and other user interface items consistently in the localized product. To make sure you are using consistent terminology, search for Microsoft approved term translations. As for language style, ensure that the target translation is natural sounding and empathetic, not robot-like.

Example:

_English_: Not enough memory to process this command.

_Our style_: :::no-loc text="内存不足，无法处理这个命令。":::

_Not our style_: :::no-loc text="没有足够的内存来处理这个命令。":::

With respect to text formatting, follow the Chinese language convention, especially in software translation. For example, the convention of translating strings with keyboard shortcuts is "translated text(&Uppercase letter)" and no space is needed between the translated text and ( ).

Example:

_English_: Exit

_Our style_: :::no-loc text="退出(&E)":::

## 7.    Use short and simple sentences

Microsoft prefers clarity and getting to the point because that manner of expression is usually friendlier and less formal. In addition, it can save space and is easy to read. Please make sure every word has a job to do, and keep the translation as concise as possible.

Example:

_English_: If you want to continue, click …

_Our style_: :::no-loc text="如要继续，请单击...":::

_Not our style_: :::no-loc text="如果希望继续进行，请单击...":::

## 8.    Avoid "translationese"

"Translationese" is overly literal or word-for-word translation. The result is awkward or ungrammatical text. When working on Microsoft projects, you may need to modify or rewrite the translated text to make it sound appropriate and natural to the audience. Be flexible and read your translation aloud to make sure your translation will be easy for the audience to read.

Example:

_English_: In short, your stuff and your info aren't limited to any single PC or device. Because you're bigger than any box.

_Our style_: :::no-loc text="总之，你的资料和信息不会受限于任何一台电脑或设备。对你而言，世界再无阻隔。":::

_Not our style_: :::no-loc text="总之，你的资料和信息不会限制于任何一个电脑或设备。因为你比他们更大。":::

Example:

_English_: Serious. Fun.

_Our style_: :::no-loc text="张弛有度。":::

_Not our style_: :::no-loc text="严肃。有趣。":::

## 9.    Use the right level of formality

Use the level of formality that is appropriate for the content. For most Microsoft products, such as games, a more informal tone should be used, and in technical texts, a more formal tone should be used. Always check with your Microsoft products contact to see what level of formality is appropriate. 

For pronouns, if it's needed, use ":::no-loc text="你":::" instead of ":::no-loc text="您":::." In text that addresses an older person or someone of a high rank or position, you can use the respectful form ":::no-loc text="您":::."

Example:

_English_: If we modify this agreement, we will send you a notice.

_Our style_: :::no-loc text="如果我们修改本协议，会向你发送通知。":::

Example:

_English_: As a guest, you can …

_Our style_: :::no-loc text="作为来宾，您可以…":::

## 10. Follow different principles for different content types

You may be asked to translate different kinds of content, such as merchandising content, advertising campaigns, PR materials, support content, and product user interface text. Each type has its own special considerations, so you should adjust your translation approach accordingly. For example, for merchandising content, apart from conciseness and clearness, it should also be interesting and engaging.

Example:

_English_: Great for work and play

_Our style_: :::no-loc text="工作娱乐两相宜":::

As for advertising campaigns, all copy should be short, simple, and direct in order to increase the credibility of the product as well as of the brand.

Example:

_English_: See something, share something

_Our style_: :::no-loc text="所见皆可共享":::

For PR materials, the copy should be faithful to the tone of the source text, but it should use the approved translations (especially the approved terminology) of key messaging.

Example:

_English_: Windows 8 can connect you to your files, photos, people, and settings, wherever you sign in.

_Our style_: :::no-loc text="无论从哪里登录，Windows 8 都能让你畅通无阻地访问文件、照片、人脉和设置。":::

Support content should be translated using the approved and established terminology in Term Studio, and then edited for readability, clarity, and accuracy.

Example:

_English_: If you're just getting started, and you need to install your printer, see Install a printer for information about how to set up your printer.

_Our style_: :::no-loc text="如果你刚开始使用并需要安装打印机，则请参阅"安装打印机"，获取有关如何设置打印机的信息。":::

In product user interface text, the tone should be light, entertaining, conversational, engaging, and authentic.

Example:

_English_: Fascinating places, winsome animals, intriguing art—find a theme that strikes your fancy.

_Our style_: :::no-loc text="找到一款主题，激发你的兴趣，让它带你领略奇异的风景胜地、活泼可爱的动物和迷人的艺术杰作。":::

Hopefully, these top 10 rules are helpful. If you have time, it is highly recommended that you read the full [Simplified Chinese Style Guide](../../reference/microsoft-style-guides.md) for more detailed information.
