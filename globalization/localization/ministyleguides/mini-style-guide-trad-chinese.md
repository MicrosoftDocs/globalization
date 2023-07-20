---
title: Traditional Chinese Localization Style Guide
description: Are you helping with translation into Traditional Chinese, but aren't able to study all the Traditional Chinese Style Guide? Here are the ten most important aspects.
ms.date: 03/04/2019
---

# Top 10 Tips for Microsoft Translation into Traditional Chinese

Are you helping with translation into Traditional Chinese, but don't have time to study all aspects of the [Traditional Chinese Style Guide](../../reference/microsoft-style-guides.md)?
Here are ten of the most important aspects to keep in mind.

## 1. Sort order

The radical (部首) is an essential element of the Chinese dictionary. The list of Chinese radicals is a rough equivalent of a Chinese "alphabet." Every Chinese character is sorted by the number of strokes (筆劃) and then by the fixed radical order for characters with the same number of strokes.

In the Index section, the following sorting order is applied:

- Digits (0–9)
- Nonalphabetic characters (for example, symbols such as ! " # $ % & ( ) * , . / : ; ? @ [ \ ])
- Characters in the English alphabet (A–Z, a–z)
- Traditional Chinese characters, ordered by the number of pen strokes

**Exception**: If the original A–Z index keys are hard-coded, you could keep the English as is and add the translation in parentheses. There is no need to capitalize the first letter.

## 2. Acronyms

When dealing with English acronyms, please apply the following general rules:

- If an acronym is used alone, please leave it as it is. (Don't add the spelled-out term even if the spelled-out form is well known.)
- If an acronym goes after a spelled-out term, please follow the format: Traditional Chinese (English acronym).
- If an acronym is used in a title, do not include the spelled-out term in the title.
- The acronym should be in all uppercase letters.
- If "s" is added at the end of an English acronym to indicate the plural, "s" should be dropped when localizing into Traditional Chinese.

## 3. Bold and italic styles

Bold and italic style should be avoided for Traditional Chinese characters. For example, italic style should be removed for localized book titles. Instead, 《》must be used to set off the book title:

Example:

_English_: :::no-loc text="For more information, see the _Office 2010 Migration Guide_":::.

_Our style_: :::no-loc text="如需詳細資訊，請參閱《Office 2010 移轉指南》。":::

_Not our style_: :::no-loc text="如需詳細資訊，請參閱 _Office 2010 移轉指南_。":::

Exceptions:

- **Bold** style for headings should be kept as is.
- **Bold** style that is used to emphasize text in strings should be kept as is.

Example:

_English_: :::no-loc text="The user **can't** be removed once all other users are removed":::.

_Our style_: :::no-loc text="移除所有其他使用者之前，**無法**移除該使用者。":::

_Not our style_: :::no-loc text="移除所有其他使用者之前，「無法」移除該使用者。":::

Bold style used to indicate user input should be kept as is.

Example:

_English_: :::no-loc text="Type **a:\setup**":::

_Our style_: :::no-loc text="輸入 **a:\setup**":::

_Not our style_: :::no-loc text="輸入a:\setup":::

_Italic_ style for placeholders should be replaced with **bold** style.

Example:

_English_: :::no-loc text="Type _password_":::

_Our style_: :::no-loc text="輸入**密碼**":::

_Not our style_: :::no-loc text="輸入_密碼_":::

For UI terms in documentation and Help, move the UI term out of the \<bold>, \<italic>, or \<ui> tag, and enclose it with half-width square brackets ([ ]).

Example:

_English_: :::no-loc text="Click **Open** to open it.":::

_Our style_: :::no-loc text="按一下 [開啟] 以開啟它。":::

_Not our style_: :::no-loc text="按一下 **開啟** 以開啟它。":::

**Exception**: For a placeholder in the UI that will be replaced by actual text or text input by the user at runtime, replace the _Italic_ style with **Bold** style per the previous instruction.

## 4. Punctuation

There are two sets of punctuation conventions that need to be followed when localizing into Traditional Chinese. One is for software and the other is for documentation.

Please refer to the following tables, and use the correct set of punctuation.

For **software**, the convention is as follows.

|Half-width|Full-width|
|---|---|
|:|，|
|;|。|
|!|、|
|?|《》|
|( )|＜＞|
|[ ]|「」|

For **documentation**, the convention is as follows.

|Half-width|Full-width|
|---|---|
| |，|
| |。|
| |、|
| |《》|
|( )|＜＞|
|[ ]|「」|
| |：|
| |；|
| |！|
| |？|

Use the English colon (:) when translating UI. The Traditional Chinese colon (：) is used in documentation, Help, and webpages.

In Traditional Chinese, please follow the rules as follows for quotation marks:

- **UI**: In US source strings, you may find software references surrounded by English quotation marks. In Traditional Chinese, UI strings should be enclosed with [ ].
- **Properties, reserved words, and parameters**: Keep the quotation marks as they appear in English. There's no need to enclose these items with [ ].
- **Titles of user guides, chapters, and sections**: Use《》for the titles of works such as books and manuals. Use ＜＞ for chapters and sections.
- **Quoted passages, new terms, and emphasis**: Use「」for these scenarios.

English parentheses ( ) are used in both software and documentation localization. There is no space between the parentheses and the text inside them.

## 5. User interface terms

When localizing UI terms in software strings, enclose the UI terms with square brackets ([ ]). As for UI terms in documentation and Help, move the UI term out of the \<bold>, \<italic>, or \<ui> tag, and enclose it with square brackets ([ ]).

**Note**: When program names or the word "Control Panel" appear in English text, those terms should be enclosed with square brackets ([ ]) only when they are used as a command to run.

The following table lists the types of items that need to be enclosed [ ] and those that should not be enclosed.

|Type|Need [ ]?|English text|Translated text|
|---|---|---|---|
|Check box|Y|:::no-loc text="Select the Match Case check box.":::|:::no-loc text="選取 [大小寫須相符] 核取方塊。":::|
|Combo box|Y|:::no-loc text="In the Font box, type or select the font that you want to use.":::|:::no-loc text="在 [字型大小] 下拉式方塊中，輸入或選取您想使用的大小。":::|
|Command button|Y|:::no-loc text="Click OK.":::|:::no-loc text="按一下 [確定]。":::|
|Menu|Y|:::no-loc text="The File menu":::|:::no-loc text="[檔案] 功能表":::|
|Window||:::no-loc text="Untitled - Notepad window":::|:::no-loc text="[未命名 - 記事本] 視窗":::|
|Folder|Y|:::no-loc text="My Favorites":::|:::no-loc text="[我的最愛]":::|
|Field|Y|:::no-loc text="the Form field":::|:::no-loc text="[表單] 欄位":::|
|Button|Y|:::no-loc text="the Unfold button":::|:::no-loc text="[展開] 按鈕":::|
|Tab|Y|:::no-loc text="On the Tools menu, click Options, and then click the View tab.":::|:::no-loc text="在 [工具] 功能表中，依序按一下 [選項] 及 [檢視] 索引標籤。":::|
|List box|Y|:::no-loc text="the Files of type list box":::|:::no-loc text="[檔案類型] 清單方塊":::|
|View|Y|:::no-loc text="Full Screen view":::|:::no-loc text="[全螢幕] 檢視":::|
|Dialog box|Y|:::no-loc text="The Options dialog box":::|:::no-loc text="[選項] 對話方塊":::|
|View (not capitalized)|N|:::no-loc text="Switch to normal view.":::|:::no-loc text="切換到標準模式":::|
|Window (not capitalized)|N|:::no-loc text="... in the document window ...":::|:::no-loc text="在文件視窗中":::|
|File|N|:::no-loc text="Open the Letter to Joe file":::|:::no-loc text="打開檔案 Letter to Joe - 或 - 打開「給喬的信」這個檔案":::|
|Location|N|C:\folder1\file.ext|C:\folder1\file.ext|
|URL|N|:::no-loc text="Please link to <https://www.microsoft.com/taiwan/> for more information.":::|:::no-loc text="如需詳細資訊，請連結至 <https://www.microsoft.com/taiwan/>":::|

## 6. Spacing

Spacing is an important consideration when localizing strings into Traditional Chinese.

The following general rules are applied:

- Half-width space is needed between Chinese characters and English letters or numbers.
- Half-width space is needed between Chinese characters and half-width punctuation marks: ( ), [ ]. **Exception**: This rule does not apply to : ; ! ?
- No space is needed around Chinese full-width punctuation marks.

## 7. Applications, products, features, and reference material

Application/product names are often trademarked or may be trademarked in the future and are therefore rarely translated. Occasionally, feature names are trademarked, too. Before translating any application, product, or feature name, please verify that it is in fact translatable and not protected in any way. This information needs to be obtained from the Microsoft team.

There are some cases where product names are translated. Such examples are packages, marketing materials, and press releases. In such cases, please follow the translations approved by the product team.

**Note**: Mistakes with product names and trademarking are Sev 1 accuracy errors.

These sources must be adhered to. Any deviation from them automatically fails a string in most cases. When more than one solution is allowed in these sources, look for the recommended one in other sections of the style guide.

- Revised Mandarin Chinese Dictionary: <http://dict.revised.moe.edu.tw>
- Dictionary of Chinese Idioms: <http://dict.idioms.moe.edu.tw>
- Academic Glossaries by the National Academy for Educational Research: <http://terms.naer.edu.tw/>
- Online Reference Materials by the National Languages Committee, Ministry of Education, R.O.C:
  - Revised Handbook of Punctuation: <http://english.moe.gov.tw/ct.asp?xItem=11428&ctNode=1873&mp=12> (For reference only; the rules described in the style guide have higher priority if there is discrepancy.)

## 8. Fictitious information

Fictitious content is legally sensitive material. The localization of fictitious content needs to follow specific legal guidelines:

**Suppliers and localizers are not allowed to create their own fictitious names.** You must either use the names in the source content or use the list of legally approved names provided by the Microsoft legal department.

If you need to use localized names, business names, product names, URLs, and more, select them from the fictitious content provided by the Microsoft legal department.

### Localizing the fictitious email alias _someone@example.com

The domain name example.com should not be localized because it is a globally recognized domain created by the IANA (Internet Corporation for Assigned Names and Numbers) for use in examples. However, according to Microsoft legal guidelines, "someone" is localizable. Consult Microsoft for the Chinese translation of _someone@example.com_.

## 9. Geopolitical concerns

Sensitive issues or issues that might offend the users in the target country or region may occur in any of the following:

- Maps
- Flags
- The names of countries or regions, cities, and languages
- Art and graphics
- Cultural content, such as encyclopedia content and other text where historical or political references are present
  
Please translate "country" as ":::no-loc text="國家/地區":::" (country/region) to avoid political issues.

A thorough understanding of the culture of the target market is required for checking the appropriateness of cultural content, clip art, visual representations of religious symbols, and body and hand gestures.

## 10. Special scenarios

When a UI term appears in the string from msiinstaller, use [\\[] for [ , and [\\]] for ].

Example:

_English_: Please click OK to continue.

_Our style_: :::no-loc text="請按一下 [\\[]確定[\\]] 繼續。":::

**Note**: This is because in .msi files, variables are enclosed in [ ]. Therefore, we need to escape the brackets.

Property names do not need to be enclosed in [ ].

Example:

_English_: The ProcessName property contains the name of the process.

_Our style_: :::no-loc text="ProcessName 屬性包含處理程序名稱。":::
