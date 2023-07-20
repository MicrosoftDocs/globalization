---
title: Russian Localization Style Guide
description: Are you helping with translation into Russian, but don't have time to study all of the Russian Style Guide? Here are the ten most important aspects.
ms.date: 05/29/2019
---

# Top 10 Tips for Microsoft Translation into Russian

Are you helping with translation into Russian, but don't have time to study all aspects of the [Russian Style Guide](../../reference/microsoft-style-guides.md)? Here are ten of the most important aspects to keep in mind.

## 1. Translate meaning not words

It's important to modify or rewrite translated strings so that they are more appropriate and natural sounding to Russian customers. To do so, please try to understand the whole intention of the sentences, paragraphs, and pages, and then rewrite just like you are writing the contents yourselves. Sometimes, you may need to remove unnecessary content or completely change idioms, jokes, and cultural references.

Example:

_English_: You'll never miss a racquetball game or forget an anniversary. And, if you click Delete, no one has to remember your birthday.

_Our style_: :::no-loc text="Вы никогда не пропустите футбольный матч и не забудете о годовщине своей свадьбы. А если нажмете кнопку **Удалить**, не обижайтесь, если никто не вспомнит о вашем дне рождения.":::

_Not our style_: :::no-loc text="Вы никогда не пропустите игру в баскетбол и не забудете о годовщине. А если нажмете кнопку Удалить, никто не обязан помнить о вашем дне рождения.":::

## 2. Simplify

Simplify both sentence structures and phrases whenever possible. Omit unnecessary words, especially such empty nouns as :::no-loc text="процедура, процесс, выполнение, операция":::, and :::no-loc text="действие":::. Do not convert verbs into the structure "generic verb + verbal noun" (that is, use :::no-loc text="отправить"::: rather than :::no-loc text="выполнить отправку":::). Use words that are commonly used in daily life, and avoid bookish, formal words. Short words such as письмо instead of :::no-loc text="сообщение электронной почты"::: are fine when needed to avoid awkward structures and repetition.

Example:

_English_: Follow these steps to change your password.

_Our style_: :::no-loc text="Чтобы сменить свой пароль, сделайте следующее.":::

_Not our style_: :::no-loc text="Для изменения пароля используйте приведенную ниже процедуру.":::

Example:

_English_: To connect …

_Our style_: :::no-loc text="Чтобы подключиться…":::

_Not our style_: :::no-loc text="Чтобы установить подключение…":::

Example:

_English_: To avoid losing all your work when stuff like that happens, make sure AutoSave is turned on:

_Our style_: :::no-loc text="Чтобы не потерять результаты своей работы в таких случаях, включите автосохранение:":::

_Not our style_: :::no-loc text="Чтобы избежать потери результатов своей работы в таких случаях, убедитесь, что автосохранение включено:":::

## 3. Choose gender-neutral language

Regardless of the audience, avoid gender stereotypes and aim to be as gender neutral as possible. Avoid using the masculine or feminine gender when referring to the user. Use neutral structures, and select verbs and adjectives that do not have a gender bias. Do not use gender endings, such as :::no-loc text="получил(-а)":::, or feminine forms, such as :::no-loc text="профессорша":::. Although Microsoft style prefers the active voice and the passive voice is to be generally avoided, it can be used to achieve gender-neutral language.

Example:

_English_: I've read and accept the terms of the license agreement.

_Our style_: :::no-loc text="Я принимаю условия лицензионного соглашения.":::

_Not our style_: :::no-loc text="Я прочитал и принимаю условия лицензионного соглашения.":::

## 4. Follow English pronouns, but adapt them to Russian style

The use of personal pronouns is a powerful way to express all the attributes of the [Microsoft voice](/style-guide/brand-voice-above-all-simple-human). Please use :::no-loc text="вы, ваш"::: (in lowercase) rather than :::no-loc text="ты, твой"::: to address the user. Third-person references, such as :::no-loc text="пользователь":::, are avoided as they sound formal and impersonal. The Russian Microsoft voice follows English (United States) voice if this does not impact grammar or create redundancy. For example, we translate "your" only in cases where it applies directly to the user or you are referring to something that belongs personally to them. We do not translate it when "your" fulfils a grammatical function or when it is obvious that something belongs to the user. Thus, we translate "your" in "your settings" (settings that the user personally made) or "your files" (the user's personal files). But we don't translate "your" in "your hand" (it's obvious that the user's, not somebody else's, hand is meant) or "connect your mouse" ("your mouse" here simply means "a mouse"). The same applies to using "I," "me," and "mine"—use them when the text focuses on the user, but do not translate each and every "I," "me," or "mine" and avoid unnatural structures. Please also remember that in some cases, "your" and "mine" correspond to the Russian pronoun ":::no-loc text="свой":::."

The usage of "we" generates the image of a team behind the software who cares about what the user is doing. Do not use :::no-loc text="корпорация Майкрософт"::: instead of :::no-loc text="мы, наш"::: in such cases. However, in technical contexts, the use of "we" might sound too personal in Russian, especially when it refers to a product or service rather than a team. In those contexts, "we" might need to be replaced by a more neutral translation.

Example:

_English_: We recommend that you back up your files on a regular basis.

_Our style_: :::no-loc text="Мы советуем вам регулярно архивировать свои файлы.":::

_Not our style_: :::no-loc text="Рекомендуется регулярно архивировать личные файлы.":::

Example:

_English_: Do you want to install this app?

_Our style_: :::no-loc text="Вы хотите установить это приложение?":::

_Not our style_: :::no-loc text="Установить это приложение?":::

Example:

_English_: We are uploading your files to the server.

_Our style_: :::no-loc text="Ваши файлы добавляются на сервер.":::

_Not our style_: :::no-loc text="Мы добавляем ваши файлы на сервер.":::

## 5. Use the active voice whenever possible

In general, use the active voice, which emphasizes the person or thing doing the action. It is more direct and personal than the passive voice, which can be confusing or sound formal. But use the passive voice to avoid a wordy or awkward construction, when the action rather than the doer is the focus of the sentence, or when the subject is unknown. Also, avoid the active voice in error messages, where the user might feel as if they are being blamed for the error.

Example:

_English_: When you save this document, it'll be updated to include changes made by other authors.

_Our style_: :::no-loc text="Когда вы сохраните этот документ, он будет обновлен с учетом изменений, внесенных другими авторами.":::

_Not our style_: :::no-loc text="Когда этот документ будет сохранен, он будет обновлен с учетом изменений, внесенных другими авторами.":::

Example:

_English_: Your app is not activated.

_Our style_: :::no-loc text="Это приложение еще не активировано.":::

_Not our style_: :::no-loc text="Вы еще не активировали свое приложение.":::

## 6. Decline nouns correctly

All program components and applications such as wizards, agents, clients, and browsers should be treated as inanimate nouns.

Example:

_English_: use a wizard

_Our style_: :::no-loc text="использовать (что?) мастер":::

_Not our style_: :::no-loc text="использовать (кого?) мастера":::

For the plural of :::no-loc text="драйвер, мастер, сервер":::, use the following standardized forms: :::no-loc text="драйверы, мастеры, серверы":::.

If the product edition names are localized, they should not be declined.

Example:

_English_: To activate Windows Professional:

_Our style_: :::no-loc text="Чтобы активировать Windows Профессиональная:":::

_Not our style_: :::no-loc text="Чтобы активировать Windows Профессиональную:":::

## 7. Know when to transliterate "Microsoft"

The word "Microsoft" is not transliterated in unlocalized product names, but in localized names, we transliterate it using the following pattern: \<Translated product name in Russian> (:::no-loc text="Майкрософт":::).

Example:

_English_: Microsoft Wallet

_Our style_: :::no-loc text="Бумажник (Майкрософт)":::

_Not our style_: :::no-loc text="Бумажник Майкрософт, Microsoft Бумажник, etc.":::

The word "Microsoft" is translated as :::no-loc text="Майкрософт"::: or :::no-loc text="корпорация Майкрософт"::: when referring to Microsoft Corporation or its products descriptively in text. The descriptor :::no-loc text="корпорация"::: can be omitted for the sake of fluency.

Example:

_English_: English: Microsoft products

_Our style_: :::no-loc text="продукты Майкрософт":::

_Not our style_: :::no-loc text="продукты Microsoft":::

The exception to this rule is in legal agreements, where "Microsoft" is left in English.

## 8. Use the correct quotation marks

Quotation marks are used when referring to UI items, such as menus and commands, if they do not have special formatting (such as bold or italic). In software, in product help, and on web pages, we use straight quotation marks (as in English). Do not use single quotation marks unless they are a part of the unlocalizable code bits. In the printed documentation, normally chevrons are used, inside chevrons straight quotation marks are used, for example, «:::no-loc text="кнопка "Готово"":::».

Example:

_English_: Click the **Start** button

_Our style_: :::no-loc text="Нажмите кнопку "Пуск"":::

_Not our style_: :::no-loc text="Нажмите кнопку «Пуск»":::

## 9. Use dashes correctly

The em-dash (—) is used as part of a predicate, to emphasize an isolated element, to introduce an element that's not essential to the meaning, and in many other grammatical functions. It is used with spaces before and after it and should not be replaced with a hyphen (-) or an en-dash (–). It is also used in non-numerical ranges, where it is followed and preceded by spaces.

The en-dash (–) has three main functions:

- It is used as a minus sign.
- It is used in number ranges without spaces before and after it.
- It is used to separate items in bulleted lists.

Example:

_English_: pages 3–5

_Our style_: :::no-loc text="стр. 3–5":::

_Not our style_: :::no-loc text="стр. 3-5, стр. 3 – 5, стр. 3—5 etc.":::

Example:

_English_: January–March

_Our style_: :::no-loc text="январь — март":::

_Not our style_: :::no-loc text="январь–март, январь—март etc.":::

Example:

_English_: Picture password is a new way to help you protect your touchscreen PC.

_Our style_: :::no-loc text="Графический пароль — это новый способ защиты компьютеров с сенсорными экранами.":::

_Not our style_: :::no-loc text="Графический пароль – это новый способ защиты компьютеров с сенсорными экранами.":::

## 10. Be careful with number placeholders

Strings with number placeholders may require different grammatical forms of words, depending on the numeric value the placeholder takes at the runtime. If separate strings are not provided for different number groups, use one of the following options:

- Change the sentence structure so that it is grammatically correct with all possible values.
- Use abbreviations.
- Change the structure in such a way that the noun is in the genitive case (it has the same forms for all plural numbers).

In any case do not use forms such as ":::no-loc text="файл(-a, -ов)":::." For "years," you should first try to find a grammatical structure that will always be correct. If it is not possible, "years" may be translated as ":::no-loc text="года":::" or ":::no-loc text="лет":::" — you are encouraged to use the most probable translation in each particular case.

Example:

_English_: %1 files are detected.

_Our style_: :::no-loc text="Найдено файлов: %1.":::

_Not our style_: :::no-loc text="Найдено %1 файл(-a, -ов).":::

Example:

_English_: %1 days left for activation.

_Our style_: :::no-loc text="На выполнение активации осталось %1 дн.":::

_Not our style_: :::no-loc text="На выполнение активации осталось %1 дней.":::

Example:

_English_: Press the button for %1 seconds.

_Our style_: :::no-loc text="Нажимайте кнопку не менее %1 секунд.":::

_Not our style_: :::no-loc text="Нажимайте кнопку %1 секунд.":::

## 10+. Use the right reference material

There is more, of course. If you are in doubt, consult the terminology, translation, and [full Russian Style Guide](../../reference/microsoft-style-guides.md) and the following references:

1. <span lang="ru">Правила русской орфографии и пунктуации. Полный академический справочник. — М.: Эксмо, 2009.
2. Толковый словарь русского языка. Например, Ожегов С. И., Шведова Н. Ю. Толковый словарь русского языка / Российская академия наук. Институт русского языка им. В. В. Виноградова. — М.: ООО «ИТИ ТЕХНОЛОГИИ», 2003.
3. Орфографический словарь. Например, Русский орфографический словарь / Российская академия наук. Институт русского языка им. В. В. Виноградова / О. Е. Иванова, В. В. Лопатин (отв. ред.), И. В. Нечаева, Л. К. Чельцова. — Москва, 2005.
4. Справочник по правописанию и литературной правке / Д. Э. Розенталь; под ред. И. Б. Голуб. — М.: Айрис-пресс, 2005.</span>

These sources are meant to provide supplementary information, background, and comparison.

1. :::no-loc text="А. Э. Мильчин, Л. К. Чельцова. Справочник издателя и автора. Редакционно-издательское оформление издания. 2-е издание, исправленное и дополненное. М.: ОЛМА-Пресс, 2003.":::
2. <http://www.gramota.ru> (Please be careful when using spravka.gramota.ru because there can be some mistakes there.)
3. <span lang="ru">Русская грамматика / АН СССР. Ин-т русского языка. Т. I-II. – М.: Наука, 1980.
4. Голуб И.Б. Стилистика русского языка. – М., 1997.</span>
