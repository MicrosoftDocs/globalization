---
title: Swedish Localization Style Guide
description: Are you helping with translation into Swedish, but don't have time to study all of the Swedish Style Guide? Here are the ten most important aspects.
ms.date: 05/13/2019
---

# Top 10 Tips for Microsoft Translation into Swedish

Are you helping with translation into Swedish, but don't have time to study all aspects of the Swedish Style Guide on the [Microsoft Language Portal](https://www.microsoft.com/Language/StyleGuides)? Here are ten of the most important aspects to keep in mind.

## 1. Sense, not words

The language in Microsoft products should have the "feel" of a product originally written in Swedish, using idiomatic syntax and terminology, while at the same time maintaining a high level of consistency. Sticking too closely to the original text will make the translation sound unnatural. The text may be split into different sentences if necessary, and you can omit descriptors to make the text snappier.

Example:

_English_: When a pinned site is launched from the taskbar, the browser frame and navigational controls integrate the site's icon and primary color, providing an experience that's tailored to the site you're viewing.

_Our style_: :::no-loc text="När du klickar på en webbplats i Aktivitetsfältet anpassas webbläsarens ram och navigeringsfält efter webbplatsen ikon och färg. På så sätt får du en skräddarsydd inramning av webbplatsen du besöker.":::

_Not our style_: :::no-loc text="När en fäst webbplats körs från Aktivitetsfältet integrerar webbläsarramen och navigeringskontrollerna webbplatsens ikon och primära färg och tillhandahåller en upplevelse som är skräddarsydd efter webbplatsen du tittar på.":::

It is also common in English to repeat words in a sentence. To achieve a natural tone in the Swedish translation, do not repeat words more than is necessary.

Example:

_English_: When using an agent, this agent is the default agent for clients when none is specified.

_Our style_: :::no-loc text="Den här agenten används som standard för klienter om inget annat anges.":::

_Not our style_: :::no-loc text="När en agent används är denna agent standardagent för klienter om inget annat anges.":::

## 2. Choices that reflect the Microsoft voice

Microsoft's brand personality comes through in our voice and tone—what we say and how we say it. Translating Swedish in a way that reflects the Microsoft voice means choosing words and grammatical structures that reflect the Microsoft style: clear and friendly, and concise without sounding robot-like. But it also means considering the needs of the audience. For example, a more informal, playful, and inspiring tone may be used for most Microsoft products and games, whereas the tone used in technical content is more formal, informative, and factual.

Example:

_English_: Fast and responsive web experiences. All-around fast.

_Our style_: :::no-loc text="Surfa snabbare och få en bättre webbupplevelse. Grym prestanda!":::

_Not our style_: :::no-loc text="Snabba och responsiva webbupplevelser. Alltid snabba.":::

## 3. Product names and terms

Before translating any application, product, or feature name, please verify that it is in fact translatable and not protected in any way. Note that product names are only very rarely localized for the Swedish market. Regarding terms, there is no need to leave a term in English if a good Swedish term is available.

Example:

_English_: firstline worker

_Our style_: :::no-loc text="service- och produktionsmedarbetare":::

_Not our style_: :::no-loc text="firstline-medarbetare":::

Example:

_English_: Microsoft Office 365 Developer Technical Preview

_Our style_: :::no-loc text="Microsoft Office 365 Developer Technical Preview":::

_Not our style_: :::no-loc text="Microsoft Office 365 Betaversion för utvecklare":::

## 4. Verbs and tense

In the US English source text, simple verb tenses help to convey the clarity of the Microsoft voice. The easiest tense to understand is the simple present, like we use in this guide. Avoid the future tense unless you are describing something that will really happen in the future and the simple present tense is inapplicable. In translations, avoid using ":::no-loc text="kommer att":::" and use the present tense instead.

Example:

_English_: If you press the button, the message will be sent.

_Our style_: :::no-loc text="Om du trycker på knappen skickas meddelandet."::: _OR_ :::no-loc text="Tryck på knappen, så skickas meddelandet.":::

_Not our style_: :::no-loc text="Om du trycker på knappen kommer meddelandet att skickas.":::

## 5. The use of pronouns

The use of personal pronouns is a powerful way to express all the attributes of the Microsoft voice. Note, that the excessive use of "we" in Swedish is not recommended. Third-person references, such as "user," are avoided as they sound formal and impersonal. Addressing the user by first- or second-person conveys the meaning that this person is not anonymous. Excessive use of the first and second pronoun (:::no-loc text="min, mitt, mina, din, ditt, dina":::) is however not recommended. Use it only when needed to clarify / distinguish (your files vs. somebody else's).

Example:

_English_: Users can change when new updates get installed.

_Our style_: :::no-loc text="Du kan ändra när uppdateringar installeras.":::

_Not our style_: :::no-loc text="Användare kan ändra när nya uppdateringar installeras.":::

Example:

_English_: You can change your settings when you have opened your program.

_Our style_: :::no-loc text="Du kan ändra inställningarna när du har öppnat programmet.":::

_Not our style_: :::no-loc text="Du kan ändra dina inställningar när du har öppnat ditt program.":::

## 6. Compounds

Generally, compounds should be understandable and clear to the user. Most Swedish speakers will find compounds of more than four or five elements difficult to interpret. Therefore, prepositions must be used to identify the relations of elements. Note that simply separating words which should be compounds is a serious error.

Example:

_English_: Supersonic aeroplane motor.

_Our style_: :::no-loc text="Motor för överljudsflygplan.":::

_Not our style_: :::no-loc text="Överljudsflygplansmotor."::: _OR_ :::no-loc text="överljud flygplans motor.":::

## 7. If and To clauses

A commonly used construction in US user guides are clauses starting with "If" or "To" followed by an imperative. Different structures are recommended in Swedish. Do not automatically translate "If you want to" with ":::no-loc text="Om du vill":::" or "To open the window" with ":::no-loc text="För att öppna fönstret":::".

Example:

_English_: If you want to open Notepad, click Start.

_Our style_: :::no-loc text="Klicka på Start för att öppna Notepad.":::

_Not our style_: :::no-loc text="För att öppna Notepad, klicka på Start.":::

Example:

_English_: Select New in the File menu to create a new document.

_Our style_: :::no-loc text="Klicka Skapa ett nytt dokument genom att välja Nytt på Arkiv-menyn.":::

_Not our style_: :::no-loc text="För att skapa ett nytt dokument, välj Nytt på Arkiv-menyn.":::

## 8. Use of commas

US English and Swedish have different punctuation rules. In Swedish, the comma is used to facilitate reading and make the text clear. Use a comma after a long subordinate clause only if it facilitates reading. Short subordinate clauses do not need a comma even if a comma is used in the English original. Always use comma before and after a parenthetical clause or phrase.

Example:

_English_: If you know the basics of MS-DOS, you can skip chapter 2.

_Our style_: :::no-loc text="Om du känner till grunderna i MS-DOS kan du hoppa över kapitel 2.":::

_Not our style_: :::no-loc text="Om du känner till grunderna i MS-DOS, kan du hoppa över kapitel 2.":::

Example:

_English_: Computer manuals, especially those for a US audience, are often unnecessarily talkative.

_Our style_: :::no-loc text="Datorhandböcker, i synnerhet amerikanska, är ofta onödigt pratiga.":::

_Not our style_: :::no-loc text="Datorhandböcker i synnerhet amerikanska är ofta onödigt pratiga.":::

## 9. Titles

In English, the titles for chapters usually begin with "How to …" or with phrases such as "Working with …" or "Using .…" Use the following guidelines for the Swedish version of Microsoft documentation.

Use the infinitive form of verbs without the infinitive marker ":::no-loc text="att":::":

Example:

_English_: Opening a document

_Our style_: :::no-loc text="Öppna ett dokument":::

_Not our style_: :::no-loc text="Att öppna ett dokument":::

For nouns in documentation headings (not chapter titles), use the same form (singular or plural) as in the source text.

Example:

_English_: Add comments to a PowerPoint presentation.

_Our style_: :::no-loc text="Lägga till kommentarer i en PowerPoint-presentation.":::

_Not our style_: :::no-loc text="Tillägg av kommentarer i en PowerPoint-presentation.":::

For the lowest-level heading that appears directly above an instruction, use the form ":::no-loc text="Så här …":::"

Example:

_English_: Saving a file

_Our style_: :::no-loc text="Så här sparar du en fil":::

_Not our style_: :::no-loc text="Att spara en fil":::

## 10. Reference materials

If you are in doubt, consult the full Swedish Style Guide and the following references:

1. Svenska datatermgruppen. Recommendations on how computer terms should be handled in Swedish. <http://www.nada.kth.se/dataterm>
2. IDG/Computer Sweden. Glossary with explanations of computer terms in Swedish. <http://cstjanster.idg.se/sprakwebben/ord.asp>
3. Rikstermbanken. Swedish terminology collection. <http://www.rikstermbanken.se/>
4. Språkrådet. General information on how to write correctly in the Swedish language. <http://www.sprakradet.se/>

Another helpful reference is the [Windows User Experience Interaction Guidelines](https://msdn.microsoft.com/library/windows/desktop/aa511258.aspx), which includes information about the user interface of Microsoft products.
