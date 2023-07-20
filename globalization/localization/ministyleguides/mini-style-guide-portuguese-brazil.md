---
title: Portuguese (Brazil) Localization Style Guide
description: Are you helping with translation into Portuguese (Brazil) but don't have time to study all of the Microsoft Portuguese (Brazil) Style Guide? Here are the ten most important aspects.
ms.date: 03/19/2019
---

# Top 10 Tips for Microsoft Translation into Portuguese (Brazil)

Are you helping with translation into Portuguese (Brazil) but don't have time to study all aspects of the [Microsoft Portuguese (Brazil) Style Guide](../../reference/microsoft-style-guides.md)? Here are ten of the most important aspects to keep in mind.

## 1. Readability and fluency

The language in Microsoft products should have the "feel" of a product originally written in Portuguese (Brazil), using idiomatic syntax and terminology, while maintaining a high level of terminological consistency. That guarantees the maximum user experience and usability for our customers. Sticking too closely to the original text will make it sound unnatural. Focus on readability and fluency, ensuring that Microsoft products are intuitive, easy to understand, and aligned with market usage in Brazil.

Try to understand the whole intention of the sentences, paragraphs, and pages, and then rewrite just like you are writing the contents yourselves.

Example:

_English_: :::no-loc text="Upload your video, and go":::

_Not our style_: :::no-loc text="Carregue o seu vídeo e vá":::

_Our style_: :::no-loc text="Carregue o seu vídeo rapidamente":::

Example:

_English_: :::no-loc text="Keep track of your friends' and family's special days.":::

_Not our style_: :::no-loc text="Controle as datas especiais dos amigos e da família.":::

_Our style_: :::no-loc text="Lembre-se dos aniversários de seus amigos e familiares.":::

## 2. Friendly and conversational tone

Microsoft's brand personality comes through in our voice and tone: what we say and how we say it. Microsoft voice targets a broad set of users from technology enthusiasts and casual computer users. Translating Microsoft voice into Brazilian Portuguese means choosing words and grammatical structures that reflect the same style as the source text. It also means considering the needs of the audience and the intent of the text. In general, the style should be clear and friendly. Use language that resembles conversation observed in everyday settings as opposed to the formal, technical language that is often used for technical and commercial content.

Example:

_English_: :::no-loc text="Stay in the know. Turn on desktop notifications.":::

_Our style_: :::no-loc text="Fique por dentro. Ative as notificações da área de trabalho.":::

## 3. Brevity

Shorter is always better. Lengthy strings of text can cause issues for localization. Be concise, without sounding robot-like. Use short, simple words. Abbreviations should be avoided as much as possible because they can make the text less intuitive.

Example:

_English_: :::no-loc text="Would you like to continue?":::

_Our style_: :::no-loc text="Quer continuar?":::

Example:

_English_: :::no-loc text="Have some fun with friends and invite them to play one of the many games online.":::

_Our style_: :::no-loc text="Convide seus amigos para jogar online.":::

## 4. Application, product, and feature names

Trademarked names and the name _Microsoft Corporation_ shouldn't be localized unless local laws require translation and an approved translated form of the trademark is available. A list of [Microsoft trademarks](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/default.aspx) is available for your reference.

Application and product names that are not descriptive names are often trademarked or can potentially be trademarked in the future. These names, therefore, are rarely translated. Occasionally, feature names that aren't descriptive are trademarked, too (for example, IntelliSense). Before translating application, product, or feature names, check the [Microsoft Language Portal](../../reference/microsoft-style-guides.md) or contact the Microsoft team.

When an application or product name contains a preposition, it's recommended that you translate the preposition, unless there are specific trademark or copyright instructions preventing the translation

Example:

_**Trademarked product name that contains a preposition**_

_English_: :::no-loc text="Microsoft Visio Pro for Office 365":::

_Our style_: :::no-loc text="Microsoft Visio Pro para Office 365"::: (Visio and Office 365 are Microsoft trademarks; the preposition is translated.)

_**Descriptive feature name**_
_English_: :::no-loc text="File Plan Manager":::

_Our style_: :::no-loc text="Gerenciador de Planos de Arquivos"::: (The feature name is translated, as it is descriptive and it is not trademarked.)

_**Trademarked feature name**_

_English_: :::no-loc text="Cortana":::

_Our style_: :::no-loc text="Cortana"::: (Cortana is not a descriptive feature name and is trademarked.)

## 5. Handling acronyms

Acronyms are words made up of the initial letters of major parts of a compound term. Some well-known examples are DNS (Domain Name Server) and HTML (Hypertext Markup Language).

**Translate** When the usage of the English acronym isn't widespread among the Brazilian audience of the product, the general recommendation is to use the spelled-out form instead.

Example:

_English_: :::no-loc text="Time Series Insights (LTS)":::

_Our style_: :::no-loc text="Time Series Insights (armazenamento a longo prazo)"::: (The spelled-out form is much more user friendly and intuitive than the acronym.)

**Don't translate** Most technical acronyms aren't translated because they are known by the target audience in Brazil in English. The localized, spelled-out form should follow the acronym the first time that the acronym appears (space permitting). In the subsequent occurrences, only the acronym should be used.  

**Note** For protocol names, file formats, and well-established acronyms, don't add the spelled-out form because the spelled-out form is rarely used.

Example:

_English_: :::no-loc text="The IR is the compute infrastructure used by Azure Data Factory to provide the following data integration capabilities across different network environments.":::

_Our style_: :::no-loc text="O IR (tempo de execução de integração) é a infraestrutura de computação usada pelo Azure Data Factory para fornecer as seguintes funcionalidades de integração de dados entre diferentes ambientes de rede.":::
(This is first time the acronym is used in the page.)

Example:

_English_: Graphic Interchange Format (.gif)

_Our style_: :::no-loc text="formato GIF":::

## 6. Capitalization

The English language tends to use title-case capitalization a lot. When localizing Microsoft products, the standard capitalization rules  for Brazilian Portuguese should be followed except for software strings. (For more details, see the following section, "Capitalization of UI strings.")

Example:

_English_

> :::no-loc text="Learning Paths":::
>
> :::no-loc text="Follow a guided learning path to build practical job skills you can start using right away.":::

_Our style_

> :::no-loc text="Roteiros de aprendizagem":::
>
> :::no-loc text="Siga um roteiro de aprendizagem guiado para desenvolver habilidades de trabalho práticas e começar a usá-las imediatamente.":::

Capitalization of topic tiles in Brazilian Portuguese is sentence case, therefore, :::no-loc text="**R**oteiros de **a**prendizagem.":::

**Capitalization of UI strings**

The source (English) capitalization is followed when translating UI labels. In some cases, this may sound unnatural for the Portuguese language, but the text in the user interface is different from other kinds of text because it's composed of strings that often have to be translated outside the context in which they appear. This rule is adopted for localization simplicity.

Example:

_English_: :::no-loc text="Clean Up Folder":::

_Our style_: :::no-loc text="Limpar Pasta":::

**Note**: This rule doesn't apply to error messages. Normally, the source text uses sentence case in error messages, but it's not rare to see error messages using title-case capitalization in the source files. For Brazilian Portuguese, sentence case should be used in error messages.

Example:

_English_: :::no-loc text="Failed to Report Event":::

_Our style_: :::no-loc text="Falha ao relatar evento":::

## 7. Pronouns

The use of personal pronouns is a powerful way to express all the attributes of the [Microsoft voice](/style-guide/brand-voice-above-all-simple-human). The user is addressed directly through the use of first- and second-person pronouns such as "you." Third-person references, such as "user," are avoided as they sound formal and impersonal. When translating into Brazilian Portuguese, address the user as _você_ instead of _usuário_ or converting the sentence to passive voice.

Avoid repeating pronouns in a sentence. In Brazilian Portuguese, omitting some pronouns when the meaning is clear from the context makes the text sound more natural.

Example:

_English_: :::no-loc text="Depending on your service agreement, you might pay more for call or text messages when your phone is roaming.":::

_Our style_: :::no-loc text="Dependendo do contrato de serviço, você pode pagar mais por ligações ou SMS quando o telefone estiver em roaming.":::

## 8. Verbs

**Don't overuse the subjunctive mode** When translating sentences that contain "Make sure" or "Ensure", it is very common to see stiff translations using the subjunctive.

Example:

_English_: :::no-loc text="Make sure to run Windows Update.":::

_Our style_: <span lang="pt-BR">Não deixe de executar o Windows Update.

**Avoid gerunds** The gerund shouldn't be used to express the notion of progressive future, as it is commonly used in English.

Example:

_English_: :::no-loc text="With the new Azure Monitor service in place, we **will be retiring** the "classic" monitoring and alerting platform.":::

_Our style_: :::no-loc text="Com o novo serviço do Azure Monitor pronto, **descontinuaremos** a plataforma de monitoramento e alerta "clássicos".":::

## 9. Punctuation

Follow the standard punctuation rules used in Brazilian Portuguese. To promote a consistent style within Microsoft products, follow these guidelines:

**UI strings** Include the final periods if they're used in the source text because you can't foresee how the strings will combine at runtime.

**Bulleted lists** Items composed of a full sentence end with a period. Items not composed of a full sentence have no period.

**Colons** Don't capitalize common words after a colon.

Example:

_English_: :::no-loc text="NOTE: This purchase can't be charged to your mobile phone account. A different payment method has been selected.":::

_Our style_: :::no-loc text="OBSERVAÇÃO: esta compra não pode ser debitada na conta do seu celular. Um outro método de pagamento foi selecionado.":::

**Commas** English and Brazilian Portuguese don't share the same rule for the use of commas in a list of three or more items. In English, a comma should be included before the conjunction. In Brazilian Portuguese, there is no comma before the conjunction.

Example:

_English_: :::no-loc text="Sync your mail, contacts, calendar, and tasks":::

_Our style_: :::no-loc text="Sincronizar seus emails, contatos, calendários e tarefas":::

## 10. Use the right reference material

There is more, of course. If you are in doubt, consult the terminology, translation, and full [Microsoft Portuguese (Brazil) Style Guide](../../reference/microsoft-style-guides.md), and the following references:

1. Academia Brasileira de Letras. Vocabulário Ortográfico da Língua Portuguesa, 5ª edição, 2009
2. Cunha, Celso e Cintra, Lindley. Nova Gramática do Português Contemporâneo. Rio de Janeiro: Editora L&PM, 2ª edição, 2009
3. Ferreira, Aurélio Buarque de Holanda. Novo Dicionário da Língua Portuguesa.Rio de Janeiro: Editora Positivo; 5ª edição, 2010
4. Instituto Antônio Houaiss. Dicionário Houaiss da Língua Portuguesa–Com a Nova Ortografia. Rio de Janeiro: Objetiva, 2009
