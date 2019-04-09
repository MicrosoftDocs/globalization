---
title: Portuguese (Brazil) Localization Style Guide
description: 
ms.date: 03/19/2019
---

# Top 10 Tips for Microsoft Translation into Portuguese (Brazil)

You are helping with translation into Portuguese (Brazil) but don't have time to study all aspects of the [Microsoft Portuguese (Brazil) Style Guide](http://download.microsoft.com/download/1/d/1/1d15d7b2-8323-4f56-b863-7acdfe4fb4cf/por-bra-StyleGuide.pdf)? Here are ten of the most important aspects to keep in mind.

## 1.	Translate sense not words

The language in Microsoft products should have the "feel" of a product originally written in Portuguese (Brazil), using idiomatic syntax and terminology, while at the same time maintaining a high level of terminological consistency. That guarantees the maximum user experience and usability for our customers. Sticking too closely to the original text will make it sound unnatural. Focus on readability and fluency, ensuring that Microsoft products are intuitive, easy to understand, and aligned with market usage in Brazil.

Try to understand the whole intention of the sentences, paragraphs, and pages, and then re-write just like you are writing the contents yourselves.

**Example**

_Translate this_: Upload your video, and go

_With this_: <span lang="pt-BR">Carregue o seu vídeo rapidamente</span>

_Not this_: <span lang="pt-BR">Carregue o seu vídeo e vá</span>

**Example**

_Translate this_: Keep track of your friends' and family's special days.

_With this_: <span lang="pt-BR">Lembre-se dos aniversários de seus amigos e familiares.</span>

_Not this_: <span lang="pt-BR">Controle as datas especiais dos amigos e da família.</span>

## 2.	Be friendly and conversational

Microsoft's brand personality comes through in our voice and tone—what we say and how we say it. Microsoft voice targets a broad set of users from technology enthusiasts and casual computer users. Translating Microsoft voice into Brazilian Portuguese means choosing words and grammatical structures that reflect the same style as the source text. It also means considering the needs of the audience and the intent of the text. In general, the style should be clear and friendly. Use language that resembles conversation observed in everyday settings as opposed to the formal, technical language that is often used for technical and commercial content. 

**Example**

_Translate this_: Stay in the know. Turn on desktop notifications.

_With this_: <span lang="pt-BR">Fique por dentro. Ative as notificações da área de trabalho.</span>

## 3.	Be concise

Shorter is always better. The increase of text length can cause issues for localization. Be concise, without sounding robot-like. Use short, simple words. Please note that abbreviations should be avoided as much as possible, as they can make the text less intuitive.

**Example**

_Translate this_: Would you like to continue?

_With this_: <span lang="pt-BR">Quer continuar?</span>

**Example**

_Translate this_: Have some fun with friends and invite them to play one of the many games online.

_With this_: <span lang="pt-BR">Convide seus amigos para jogar online.</span>

## 4.	Application, product, and feature names

Trademarked names and the name _Microsoft Corporation_ shouldn't be localized unless local laws require translation and an approved translated form of the trademark is available. A list of [Microsoft trademarks](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/default.aspx) is available for your reference.

Application and product names that are _not_ descriptive names are often trademarked or can potentially be trademarked in the future and are, therefore, rarely translated. Occasionally, feature names that are not descriptive are trademarked as well (e.g., IntelliSense). Before translating application, product, or feature names, check the [Microsoft Language Portal](https://www.microsoft.com/en-us/Language/StyleGuides) or contact the Microsoft team.

When an application or product name contains a preposition, it is recommended to translate the preposition, unless there are specific trademark/copyright instructions preventing the translation.

**Example**

_**Trademarked product name that contains a preposition**_

_English_: Microsoft Visio Pro for Office 365 → _Brazilian Portuguese_: <span lang="pt-BR">Microsoft Visio Pro para Office 365</span>
(Visio and Office 365 are Microsoft trademarks; the preposition is translated.)

_**Descriptive feature name**_
_English_: File Plan Manager → _Brazilian Portuguese_: <span lang="pt-BR">Gerenciador de Planos de Arquivos</span>
(The feature name is translated, as it is descriptive and it is not trademarked.)

_**Trademarked feature name**_

_English_: Cortana → _Brazilian Portuguese_: <span lang="pt-BR">Cortana</span>
(Cortana is not a descriptive feature name and is trademarked.)

## 5.	Handling acronyms

Acronyms are words made up of the initial letters of major parts of a compound term. Some well-known examples are DNS (Domain Name Server) or HTML (Hypertext Markup Language).

**Translate** When the usage of the English acronym is _not_ widespread among the Brazilian audience of the product, the general recommendation is to use the spelled-out form instead. 

**Example**

_Translate this_: Time Series Insights (LTS)

_With this_: <span lang="pt-BR">Time Series Insights (armazenamento a longo prazo)</span> (The spelled-out form is much more user friendly and intuitive than the acronym.)

**Do not translate** Most technical acronyms are not translated, as they are known by the target audience in Brazil in their English form. The localized spelled-out form should follow the acronym the first time the acronym appears (space permitting). In the subsequent occurrences, only the acronym should be used. 

**Note**: For protocol names, file formats, and well-established acronyms, do not add the spelled-out form, as the spelled-out form is rarely used.

**Example**

_Translate this_: The IR is the compute infrastructure used by Azure Data Factory to provide the following data integration capabilities across different network environments:

_With this_: <span lang="pt-BR">O IR (tempo de execução de integração) é a infraestrutura de computação usada pelo Azure Data Factory para fornecer as seguintes funcionalidades de integração de dados entre diferentes ambientes de rede:</span>
(This is first time the acronym is used in the page.)

**Example**

_Translate this_: Graphic Interchange Format (.gif)

_With this_: <span lang="pt-BR">formato GIF</span>

## 6.	Use of capitalization

The English language tends to do extensive use of title case capitalization. When localizing Microsoft products, the standard capitalization rules for Brazilian Portuguese should be followed except for software strings.

**Example**

_Translate this_

> Learning Paths
>
> Follow a guided learning path to build practical job skills you can start using right away.

_With this_

> <span lang="pt-BR">Roteiros de aprendizagem
>
> Siga um roteiro de aprendizagem guiado para desenvolver habilidades de trabalho práticas e começar a usá-las imediatamente.</span>

Capitalization of topic tiles in Brazilian Portuguese is sentence case, therefore, <span lang="pt-BR">Roteiros de aprendizagem.</span>

**Capitalization of UI strings**

The source (English) capitalization is followed in UI options. In some cases, this may sound unnatural for the Portuguese language, but the text in the user interface follows a different nature, as it is composed of strings, which often times have to be translated decontextualized. This rule is adopted for localization simplicity.

**Example**

_Translate this_: Clean Up Folder

_With this_: <span lang="pt-BR">Limpar Pasta</span>

**Note**: This rule does not apply to error messages. Normally, the source text uses sentence case in error messages, but it is not rare to see error messages using title case capitalization in the source files. For Brazilian Portuguese, sentence case should be used in error messages.

**Example**

_Translate this_: Failed to Report Event

_With this_: <span lang="pt-BR">Falha ao relatar evento</span>

## 7.	Pronouns

The use of personal pronouns is a powerful way to express all the attributes of the [Microsoft voice](https://docs.microsoft.com/en-us/style-guide/brand-voice-above-all-simple-human). The user is addressed directly through the use of first- and second-person pronouns such as "you." Third-person references, such as "user," are avoided as they sound formal and impersonal. When translating into Brazilian Portuguese, address the user as "você" instead of "usuário" or converting the sentence to passive voice.

For more fluent text, avoid redundancy of pronouns in a sentence. In Brazilian Portuguese, omitting some pronouns when the meaning is implicit in the context makes the text more natural.

**Example**

_Translate this_: Depending on your service agreement, you might pay more for call or text messages when your phone is roaming.

_With this_: <span lang="pt-BR">Dependendo do contrato de serviço, você pode pagar mais por ligações ou SMS quando o telefone estiver em roaming.</span>

## 8.	Verbs

**Don't overuse the subjunctive mode** When translating sentences that contain "Make sure" or "Ensure", it is very common to see stiff translations using the subjunctive.

**Example**

_Translate this_: Make sure to run Windows Update.

_With this_: <span lang="pt-BR">Não deixe de executar o Windows Update.

**Avoid gerundism** The gerund should not be used to express the notion of progressive future, as it is commonly used in English.

**Example**

_Translate this_: With the new Azure Monitor service in place, we **will be retiring** the "classic" monitoring and alerting platform.

_With this_: <span lang="pt-BR">Com o novo serviço do Azure Monitor pronto, **descontinuaremos** a plataforma de monitoramento e alerta "clássicos".</span>

## 9.	Punctuation

Follow the standard punctuation rules used in Brazilian Portuguese. To promote a consistent style within Microsoft products, follow these guidelines:

**UI strings** Follow the source text use of final periods, as we cannot foresee how the strings will combine at run-time.

**Bulleted lists** Items composed of full sentences are followed by a period in the end of the sentence. Items not composed by full sentence have no period.

**Colons** Do not capitalize common words after a colon. 

**Example**

_Translate this_: NOTE: This purchase can't be charged to your mobile phone account. A different payment method has been selected.

_With this_: <span lang="pt-BR">OBSERVAÇÃO: esta compra não pode ser debitada na conta do seu celular. Um outro método de pagamento foi selecionado.</span>

**Commas** English and Brazilian Portuguese don't share the same punctuation rule in a list of three or more items. In English, a comma should be included before the conjunction. In Brazilian Portuguese, there is no comma before the conjunction. 

**Example**

_Translate this_: Sync your mail, contacts, calendar, and tasks

_With this_: <span lang="pt-BR">Sincronizar seus emails, contatos, calendários e tarefas</span>

## 10.	Use the right reference material

There is more, of course. If you are in doubt, consult the terminology, translation, and full [Microsoft Portuguese (Brazil) Style Guide](http://download.microsoft.com/download/1/d/1/1d15d7b2-8323-4f56-b863-7acdfe4fb4cf/por-bra-StyleGuide.pdf), the [Microsoft Language Portal](https://www.microsoft.com/en-us/Language/StyleGuides), and the following references:
1.	Academia Brasileira de Letras. Vocabulário Ortográfico da Língua Portuguesa, 5ª edição, 2009
2.	Cunha, Celso e Cintra, Lindley. Nova Gramática do Português Contemporâneo. Rio de Janeiro: Editora L&PM, 2ª edição, 2009
3.	Ferreira, Aurélio Buarque de Holanda. Novo Dicionário da Língua Portuguesa.Rio de Janeiro: Editora Positivo; 5ª edição, 2010
4.	Instituto Antônio Houaiss. Dicionário Houaiss da Língua Portuguesa–Com a Nova Ortografia. Rio de Janeiro: Objetiva, 2009
