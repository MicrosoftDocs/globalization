---
title: Czech Localization Style Guide
description: Are you helping with translation into Czech, but don't have time to study all aspects of the Czech Style Guide on the Microsoft Language Portal? Here are ten of the most important aspects to keep in mind.
ms.date: 03/04/2019
---

# Top 10 Tips for Microsoft Translation into Czech

Are you helping with translation into Czech, but don't have time to study all aspects of the Czech Style Guide on the [Microsoft Language Portal](https://www.microsoft.com/Language/StyleGuides)? Here are ten of the most important aspects to keep in mind.

## 1. Microsoft voice

The [Microsoft voice](/style-guide/brand-voice-above-all-simple-human) is warm and relaxed, crisp and clear, and ready to lend a hand. Write short, easy-to-read sentences. Avoid the passive voice. Be pleasant, and ensure that explanations are appropriate for the target audience and as enjoyable to read as is possible. Avoid slang, and be careful with colloquialisms—it is acceptable to reassure and connect with customers in a conversational tone, but be professional in doing so.

Be brief and get straight to the point. Do not translate literally. Use language that resembles conversation observed in everyday settings as opposed to the formal, technical language that is often used for technical and commercial content. To guide your translation, consider the intent of the text and what the customer needs to know to successfully complete the task.

**Example**

_English_: Crashes happen. The power goes out. The network goes down.

_Our style_: <span lang="cs">Bohužel není vždycky všechno bez problémů. Může vám spadnout počítač, vypnou elektřinu nebo vypadne síť.</span>

_Not our style_: <span lang="cs">Havárie se stávají. Dojde k výpadku elektrické energie. Může být nedostupná síť.</span>

## 2. Level of formality

Avoid words and phrases that sound too formal. Either look for more informal alternatives, or translate the source text in a way that will allow you to omit the problematic formal word or phrase. However, you still need to assess the appropriate tone for each text. The choice of words will depend on what level of formality is appropriate for the Czech target text.

**Example**

_Our style_: <span lang="cs">ale, přestože, sice, už, který, dál, nejdřív, nejde, teď, zkusit znovu, potom, jestli, tady, zrušit, pokud chcete, …</span>

_Not our style_: <span lang="cs">ač, avšak, již, jež, nadále, nejprve, nelze, nyní, opakovat akci, poté, zda, zde, chcete-li, storno, …</span>

## 3. Word-for-word translation

In order to achieve a fluent translation, you should avoid translating word for word. At first, you need to understand the meaning of the whole text or paragraph. Czech and English have different language structures, so strictly following the original does not produce a good result in Czech. Such translation often sounds stiff and unnatural or does not make sense at all. It is a good idea to check the source in the live pages. You can also split longer English sentences into shorter ones, or combine short English sentences into longer, more fluid ones.

**Example**

_English_: Users can control their desktops.

_Our style_: <span lang="cs">Uživatelé si můžou upravit plochu podle svých představ.</span>

_Not our style_: <span lang="cs">Uživatelé mohou řídit vzhled své plochy.</span>

**Example**

_English_: Protect your files in case of a crash–turn on AutoRecover and AutoSave

_Our style_: <span lang="cs">Zapnutí automatického obnovení a automatického uložení (abyste nepřišli o soubory, když vám spadne počítač)</span>

_Not our style_: <span lang="cs">Ochrana vašich souborů pro případ chyby – zapnutím automatického obnovení a automatického uložení</span>

## 4. Gender

Please consult the Czech grammar rules at <http://prirucka.ujc.cas.cz/> to confirm the use of a new loan word and its proper grammatical categories.

When addressing the user, ensure gender neutrality by means of the second-person plural.

**Example**

_English_: Ensure you have closed all the files.

_Our style_: <span lang="cs">Ujistěte se, že jste zavřeli všechny soubory.</span>

However, there are situations where gender cannot be avoided or the expression of both genders is preferred instead of using the neutral form with the descriptor _<span lang="cs">uživatel</span>_ (for example, in content with a less formal tone). In such a case, include both the masculine and feminine gender.

**Example**

_English_: {ut1} has updated this group with a better chat experience.

_Our style_: <span lang="cs">{ut1} aktualizoval(a) tuto skupinu novou verzí chatu.</span> _or_ <span lang="cs">{ut1} aktualizoval/a tuto skupinu novou verzí chatu.</span>

In dynamic strings, such as the greeting in a mail-merge document, it is recommended to omit the user name placeholder entirely or use both genders (or both, as appropriate) to ensure gender neutrality. Note that the feminine form precedes the masculine.

**Example**

_Our style_: <span lang="cs">Vážená paní / Vážený pane</span>

## 5. Terminology and glossaries

To maintain consistency in key terms, technical terms, and product names, use approved terminology. If you feel that an approved term doesn't fit with the Microsoft voice, send your concerns to your project manager.

## 6. Acronyms

Acronyms are words made up of the initial letters of major parts of a compound term. Some well-known examples are DNS (Domain Name Server) and HTML (Hypertext Markup Language). Acronyms do not include periods in Czech.

In longer texts, it is advisable to spell out the acronym in parenthesis on its first appearance in the text. For subsequent occurrences, only the acronym is used.

### Localized acronyms

In localization contexts, very few acronyms are translated. They include only well-established and familiar expressions that occur commonly outside technical contexts. Localized acronyms do not require a declinable descriptor.

**Example**

_English_: Such operations will require consultations within the UN and the OSCE.

_Our style_: <span lang="cs">Taková operace se neobejde bez konzultací v rámci OSN a OBSE.</span>

### Unlocalized acronyms

These are not integrated into the syntactic structure of the sentence and do require a descriptor word.

**Example**

_English_: The function is affected by the BIOS error.

_Our style_: <span lang="cs">Funkci ovlivňuje chyba systému BIOS.</span>

## 7. Possessives

English tends to use many more possessive pronouns than Czech does. Because possessives can function as determiners in English, they are often used interchangeably with the definite article. That is, possessives are often used in a somewhat generic sense, rather than with the primary purpose of attribution. In such cases, it is often possible to omit the pronoun from the translation entirely.

When you include the possessive, keep in mind that the reflexive form _svůj_ is used when the governing noun is being attributed to the subject of the sentence. This is a common source of errors, especially when the subject is implied, not explicitly named in the sentence.

**Example**

_English_: A new window appears on your desktop.

_Our style_: <span lang="cs">Na ploše se otevře nové okno.</span>

**Example**

_English_: Download the file to your computer.

_Our style_: <span lang="cs">Stáhněte si soubor na svůj počítač.</span>

**Example**

_English_: The email server rejected your username.

_Our style_: <span lang="cs">E-mailový server odmítl vaše uživatelské jméno.</span>

## 8. Progressive action

Use the reflexive _se_ to express statements of progressive actions.

**Example**

_English_: Waiting for server …

_Our style_: <span lang="cs">Čeká se na server…</span>

_Not our style_: <span lang="cs">Čekání na server…</span>

**Example**

_English_: Checking compatibility …

_Our style_: <span lang="cs">Kontrolujte se kompatibilita…</span>

_Not our style_: <span lang="cs">Probíhá kontrola kompatibility…</span>

However, if the subject of the segment is unexpressed, use the general style guide rule for progressive action.

**Example**

_English_: Saving …

_Our style_: <span lang="cs">Ukládání…</span>

**Example**

_English_: Waiting …

_Our style_: <span lang="cs">Systém/aplikace čeká…</span>

## 9. Declining product names

In some cases, it is appropriate to decline the product name. But in some cases the product name should not be declined, and in this case an appropriate generic word should be used before the product name, and this generic word should be declined. However, never use the _-ovský/á/é_ endings (_wordovský_, _excelovský_, _accessovská_, _outlookovský_), although they are also grammatically correct.

**Example**

_Examples of declined product names_

- ve Wordu
- v Microsoft Excelu
- ve Skypu
- v Bingu
- na Facebooku
- v Exchangi
- wordový dokument (also dokument Wordu, dokument z Wordu, dokument aplikace Word)
- excelový sešit
- instalace Office
- skypové číslo/jméno
- skypová zpráva/hovor…

_Examples of product names that should not be declined_

- v Office
- kredit Skype
- účet Skype…

## 10. Reference materials

There are plenty of other sources that can help you deliver the best result. You can also find more information about Microsoft writing style in general in the [Microsoft Writing Style Guide](/style-guide/welcome/whats-new). Other sources, apart from those already mentioned, include:

1. <http://prirucka.ujc.cas.cz/>
2. <https://www.korpus.cz/>
3. <http://www.ujc.cas.cz/oddeleni/index.php?page=poradna>
4. <https://support.skype.com/en/>
