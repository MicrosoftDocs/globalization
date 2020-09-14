---
title: Korean Localization Style Guide
description: Are you helping with translation into Korean, but don't have time to study all aspects of the Korean Style Guide on the Microsoft Language Portal? Here are ten of the most important aspects to keep in mind.
ms.date: 05/13/2019
---

# Top 10 Tips for Microsoft Translation into Korean

This is a mini style guide for the translation of Microsoft content into Korean. This contains a brief overview of the style, so check the [full style guide](https://www.microsoft.com/ko-kr/language/StyleGuides) for more details. 

Feel free to choose your own words to convey the intention of the original text. Do not restrict yourself to the "rigid" writing style that is traditionally used in the computer industry. The translation should sound natural and be easy to understand, as if one Korean person is speaking to another.


## 1.	Warm and relaxed

Use familiar, everyday language rather than the formal and technical language that is typically used in IT documents. Rather than using difficult Chinese characters, use Korean expressions that are easy to understand.

Avoid using verbs like "<span lang=ko>수행</span>," "<span lang=ko>실행</span>," and "<span lang=ko>제공</span>" as expressions of descriptive nouns (<span lang=ko>작동, 동작, 설치, 제거, 검색, 감사</span>, and so on). And use "<span lang=ko>~세요</span>" instead of "<span lang=ko>~십시오</span>" as an ending form to properly address the tone and register. But you should use "<span lang=ko>~십시오</span>" when localizing license agreements or other legal content to express a formal tone.

**Example**

_Our style_: <span lang=ko>다음 단원을 참조하세요.</span>

_Not our style_: <span lang=ko>다음 단원을 참조하십시오.</span>

**Example**

_Our style_: <span lang=ko>파일을 사용하지 마세요.</span>

_Not our style_: <span lang=ko>파일을 사용하지 마십시오.</span>

**Example**

[Legal content]

_Our style_: <span lang=ko>Microsoft는 이러한 추가 조건에 관한 책임을 지지 않으므로 제3자가 귀하에게 제공한 모든 추가 조건을 검토하십시오.</span>

_Not our style_: <span lang=ko>Microsoft는 이러한 추가 조건에 관한 책임을 지지 않으므로 제3자가 귀하에게 제공한 모든 추가 조건을 검토하세요.</span>

## 2.	Crisp and clear
Write short and easy-to-read sentences. Avoid the passive voice; it is difficult to read and understand quickly. For example, use "<span lang=ko>됩니다" rather than "<span lang=ko>되어집니다</span>" and use "<span lang=ko>부르는</span>" rather than "<span lang=ko>불리는</span>."

Use the kind of short, simple words that are spoken in everyday conversations. Short words also save space on-screen and are easier to read quickly. Try to use everyday words that customers in the Korean market are already accustomed to.

**Example**

_English_: Email address

_Our style_: <span lang=ko>메일 주소</span>

**Example**

_English_: Online store

_Our style_: <span lang=ko>온라인 스토어</span>

**Example**

_English_: Home page

_Our style_: <span lang=ko>홈페이지</span>

## 3.	A natural tone and fluent translation

To achieve a fluent translation, avoid word-for-word translation. Strict word-for-word translation would make the tone stiff and unnatural. Understand the context, and paraphrase it whenever necessary. Sometimes you can omit descriptors to make the text snappier. But make sure that you don't distort the intention of the original text.

**Example**

_English_: Great for work and play

_Our style_: <span lang=ko>업무와 여가를 함께</span>

_Not our style_: <span lang=ko>일과 놀이에 알맞음</span>

**Example**

_English_: These laptops are lightweight and loaded with memory so you can move fast and get work done when you have to—but also have beautiful displays and big sound, so you can sit back and enjoy HD movies when you want to.

_Our style_: <span lang=ko>가벼우면서도 넉넉한 메모리를 제공하기 때문에 가지고 다니면서 필요할 때 작업할 수 있으며, 편한 자세로 앉아 HD 영화를 감상할 수도 있습니다.</span>

_Not our style_: <span lang=ko>이러한 랩톱은 가볍고 메모리가 탑재되어 있으므로 빠르게 이동할 수 있고 필요할 때 작업을 완료할 수 있을 뿐만 아니라 멋진 디스플레이와 큰 사운드를 제공하여 원하는 때에 앉아서 HD 영화를 즐길 수 있습니다.</span>

## 4.	UI and UE terms and error messages

### UI content

When localizing user interface (UI) terms in software strings, enclose the UI terms in square brackets ([ ]). If the source uses double quotation marks, though, please apply the same style in the target (unless otherwise flagged by Microsoft as an exception). 

### UE content

When UI terms are referenced in user education (UE) content (that is, documentation and online Help), follow the same formatting as the English text. That is, if a bold font is used for the English UI terms in documentation, apply the same bold formatting to the Korean UI terms. Bold formatting can be applied the same as in English, but it is recommended that you remove any italic formatting, for better readability.

### Error messages

In general, error messages are translated into "<span lang=ko>~니다</span>" style, in which case, a period should be placed at the end of the Korean text even if the English sentence ends with different punctuation, such as a colon. However, if the English text is not a full sentence but rather a phrase, or it ends with a colon + placeholder, you can translate the text accordingly.

## 5.	Country/regional standards

### Currency

Use one of the following options when monetary amounts are given in Korean currency:
-	<span lang=ko>5,360.02원</span>
-	<span lang=ko>₩5,360.02</span>

### Date and time

Use the "yyyy-mm-dd" format.

**Example**

_English_: 26-May-2019

_Our style_: 2019-05-26

### Measurement units

Follow the metric system (that is, meters, liters, and Celsius), which is formally recognized and widely used in Korea.

**Note**: English units such as inch, feet, mile, and gallon are no longer officially accepted in Korea. Traditionally, "inch" was used a lot while "mile" and "feet" were rarely used. As of July 2007, the Korean government has started enforcing the use of the metric system more vigorously, so you may be fined if you use the English units in public documents or products. They should be replaced with their counterpart (meter and liter) in the [standard metric system](https://www.calculateme.com/).

**Example**

_English (US)_: 5.5 inches

_Our style_: 13.97cm

**Example**

_English (US)_: 10 oz.

_Our style_: 0.3L

## 6.	Brand, product, and feature names and trademarks

### Brand, product, and features names

Product names and brand names are normally not translated. Even when a product name or brand name is translated, don't translate the names "Windows" or "Microsoft." Feature names can usually be translated. Always confirm with the project team whether a name can be localized.

### Trademarks

Trademarked names and the name Microsoft Corporation shouldn't be localized unless local laws require translation and an approved translated form of the trademark is available. A [list of Microsoft trademarks](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/default.aspx) is available for your reference.

**Example**

_English_: accessibility

_Our style_: <span lang=ko>접근성</span>

_Not our style_: <span lang=ko>내게 필요한 옵션</span>

**Example**

_English_: trusted connection

_Our style_: <span lang=ko>신뢰할 수 있는 연결</span>

_Not our style_: <span lang=ko>트러스트된 연결</span>

**Example**

_English_: Windows Movie Maker

_Our style_: <span lang=ko>Windows 무비메이커</span>

_Not our style_: <span lang=ko>윈도우 무비메이커</span>

## 7.	Translation of version strings

Product, feature, and component names are often located in the so-called "version strings" that appear in the software. Version strings that contain copyright information should always be translated. But note that some trademarks and brand, product, and corporate names should remain in English in version strings. Please refer to Term Studio for more details.

**Example**

_English_: © 2019 Microsoft Corporation. All rights reserved.

_Our style_: <span lang=ko>© 2019 Microsoft Corporation. 모든 권리 보유.</span>

## 8.	Abbreviations

Don't abbreviate the following words:
- Do not abbreviate "Microsoft” as "MS." 
- Do not abbreviate "Internet Explorer" as "IE."
- Do not abbreviate "Visual Studio" as "VS" in product names. 
- Do not abbreviate the names of operating systems.

**Example**

_English_: Need assistance with your Microsoft product? 

_Our style_: <span lang=ko>Microsoft 제품에 대해 도움이 필요하세요?</span>

_Not our style_: <span lang=ko>MS 제품에 대해 도움이 필요하세요?</span>

## 9.	Acronyms

### Localized acronyms

When the Korean translation of the spelled-out form of an English acronym is commonly used, keep the acronym in English, but spell out the term in Korean. 

When translating acronyms, refer to the term lists and glossaries listed later in this guide or to relevant websites to find the correct Korean translation. 

The English acronym should always come first, followed by the Korean translation in parentheses. 

**Example**

_English_: USB (Universal Serial Bus)

_Our style_: <span lang=ko>USB(범용 직렬 버스)</span>

**Example**

_English_: (IIS) Internet Information Services

_Our style_: <span lang=ko>IIS(인터넷 정보 서비스)</span>

**Example**

_English_: distinguished name (DN)

_Our style_: <span lang=ko>DN(고유 이름)</span>

### Acronyms that are not localized

When the Korean version of the spelled-out term is not common, keep both the acronym and the spelled-out term in English. The English acronym should always come first, followed by its full spelling in parentheses, regardless of how the acronym appears in the English source.

**Example**

_English_: Microsoft Management Console (MMC)

_Our style_: MMC (Microsoft Management Console)

**Example**

_English_: Open Database Connectivity (ODBC)

_Our style_: ODBC (Open Database Connectivity)

**Example**

_English_: Definition Language (RDL)

_Our style_: RDL (Report Definition Language)

## 10.	Reference materials

If you have questions, consult the terminology, translation and style guide. 

**Note**: Please be careful when using Microsoft glossaries for general marketing content. As a general rule, except for UI and software references, you are not required to follow the translations listed in the Microsoft glossaries. In particular, be aware that some unpopular or outdated terms can still be found there, and avoid them. Do not automatically use the translations in these glossaries. Instead, use terminology that is common in everyday speech. (But do not use slang.)
