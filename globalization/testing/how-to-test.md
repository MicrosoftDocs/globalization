---
title: How to test localized products
description: Defining a process for localization testing, identifying tools that can help with testing, and creating test data help ensure that testing identifies issues.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# How to test localized products

This article discusses the methods and tools for testing your localized products. For information about localizability testing, that is, what you should validate before starting localization, see [When to test internationalized products](when-to-test.md) and [What to look for when testing internationalized products](what-to-look-for-when-testing.md).

## Localization testing

Localization testing checks how well your product is translated into a particular target language. Localization testing is an extension of [localizability testing](when-to-test.md), where the functional support for locales was already verified.

[Pseudolocalization](../methodology/pseudolocalization.md) is a powerful tool for uncovering many issues during localizability testing. When you [test for localizability](when-to-test.md) before you localize, the chances of having serious functional problems after localization are reduced. However, pseudolocalization doesn't eliminate the need for functional testing of a localized application. You must still check that the application you're shipping to a particular market really works in that language and locale. But it takes less time and fewer resources.

### General areas of focus in localization testing

Localization testing should focus on several general areas.

The first involves things that are often changed during localization, such as the user interface (UI) and user assistance content.

The second consists of culture-specific, language-specific, and country- or region-specific areas. Examples include configurable components such as region defaults and the default language, as well as language-specific and region- or market-specific functionality, for example, spelling checkers and speech engines. You should also test the availability of drivers for local hardware.

Pay specific attention to customization that couldn't be automated using the infrastructure provided by your platform or language globalization services. For example, check that the formatting of mailing addresses matches the locale conventions.

The ordering of names is another good example. The order in which surname and first name appear varies according to country and region. For instance, some Muslim countries and certain regions in India use a different name order than that used in English. People might have single names, multi-part names, or names that otherwise don't fit the first-last pattern.

You also need to check that everything you're going to release to a new target market complies with the local laws and regulations. This includes not only the license agreement but also any user documentation. The use of encryption   can be regulated in certain regions, so check that it's used in conformance to local regulations.

### Localization testing for UI and language

Localization testing for your product’s UI and language-related items should:

- Validate all application resources, including strings and translated images.
- Verify linguistic accuracy. For more information, see [Linguistic validation](#linguistic-validation).
- Check that printed documentation, online help, messages, interface resources, and keyboard shortcuts   are consistent with each other. If you have shipped localized versions of your product before, make sure that the translation is consistent with the earlier released versions.
- Confirm adherence to system, input, and display environment standards.
- Check the usability of the UI.
- Assess cultural appropriateness.
- Check for politically sensitive content.
- Ensure the market-specific information about your company, such as contact information or local product-support phone numbers, is correct.  

## Test tools

Test tools, especially automated tools, play an essential role in the testing process. While automated testing can't completely replace manual testing, many test areas gain tremendous benefits from automation. For instance, using automated test tools is an effective way to verify the functionality of a localized product. Automated tests can validate the degree of a product's globalization.

Running automated tests on the original and localized applications side by side can verify that localization doesn't break any functionality. With automation, you don't need to understand the language of the localized UI since the tools can test the functionality regardless of the language. For instance, "Select the default button" is a test of functionality that can work for any language.

Ensuring that a product is globalized requires the ranges of test input to be extended, and environment settings to be more diverse. Automation makes it easier to deal with the additional test cases and allows you to efficiently track the results. Restoring the locale settings or test input that brought about an error in a program also becomes easier.

### Globalized test tools

Automation of test runs involves more than just running your usual test tools on your new product under a globalized environment. Test tools that check the functionality of your app UI can be broken when the tested application is translated. Even when not affected by translation, test results might be incorrect if the tool verifies locale-formatted data and assumes that the data format is fixed. For example, in globalized applications, the date format varies according to locale and region. For more information, see Locale and culture. The [In-context review](#in-context-review)inability to use international test data can make a test tool unusable.

To avoid these and similar problems, developers of test tools must follow the same rules as the developers of globalized software do. Test tools must be globalized, adjust themselves dynamically to locale settings, and process international text data. If they must access localizable objects by name, the test tools must also be localized.

Experience shows that some tools are easy to globalize, while others aren't. More advanced programming models usually provide better ways to make the code universal regarding locale and language settings.

## Linguistic validation

Linguistic validation is an important step in ensuring quality translations of your product and documentation. In this phase, a target language expert reviews translations to ensure that they're correct.

Performing linguistic validation can be a critical early step when you first engage a translation supplier or localize a new language. Early linguistic validation is typically focused on samples of localized resources and content in isolation. Later, an [in-context review (ICR)](#in-context-review) can be conducted with the running application. Ideally, you complete both early linguistic validation and in-context reviews before release.

Linguistic validation should be performed by native speakers of the language. Using in-country/region reviewers is highly recommended to ensure that the localized content is aligned with target market expectations.

A linguistic reviewer looks at the following aspects:

| Aspect | Description |
|--------|-------------|
| Source quality | Is the source text well-written? Poor quality source material makes translation difficult. |
| Grammar and spelling | Is the translation grammatically correct and uses the proper spelling? |
| Accuracy | Does the translation accurately represent the intent and meaning of the source text? If it doesn't, is the resource missing annotations to provide the context? |
| Contextual adherence | Is the translation appropriate for the context it appears in? |
| Style guide adherence | Does the tone and vocabulary of the translation adhere to the project's style guide? |
| Terminology and vocabulary | Is the terminology correct and suitable for the target audience? |
| Consistency | Are the same ideas and terminology used consistently across the translations? |
| Cultural appropriateness | Is the translation a good fit for the target culture? The translation might be too literal a translation of the source text. |
| Correct formats for data | Is the formatting of data correct for the target culture? |

While linguistic validation is primarily focused on the linguistic and cultural aspects of the translation, the reviewer might observe other problems that can occur because of localization. All issues should be recorded and reported in the review process.

The following recommendations can improve the effectiveness of linguistic validation:

- If the volume of translated material is high, a complete review might be too expensive or time-consuming. In such a case linguistic reviewers might examine only samples of the translations. Samples might be chosen randomly or focus on known or probable problem areas.
- Reviewers should have good communication with the product team to get answers to their questions or resolve ambiguities.
- Consider whether to use the same translation supplier or engage a third-party reviewer to ensure objective validation.
- Many languages are spoken in multiple countries, regions, and cultures, so review expectations need to be clearly set. For example, Spanish, French, and Arabic are spoken in multiple countries and regions, with significant vocabulary and terminology differences. The most common strategy for such languages is to release a single "neutral" version of the language that can be adapted to the various target markets. For some languages like Portuguese, the differences between regions are so significant that "neutral" language might not be appropriate.
- In-country/region reviews also help validate the need for adding extra language variants to cater for significant linguistic differences among markets. Market size and terminology differences could be factors in choosing to add a specific variant of a language, such as for French for Canada, and Spanish for Mexico.

## In-context review

In-context review (ICR) can be the key to ensuring a high quality localized and translated experience for international users. ICR means performing [linguistic validation](#linguistic-validation) in the context of the running application. For documentation, the reviewer uses the same presentation medium that end users see. Performing linguistic validation in the context of the user's experience catches more problems than doing it at the resource level.

The criteria for choosing in-context reviewers are the same as for [linguistic validation](#linguistic-validation).

### How to perform ICR

The reviewers should be provided with the following resources:

- Access to the working localized application.
- Your product style guides and glossary.
- Product documentation in both the source language and the target language.
- An agreed format and tool for recording and reporting issues. Issue reporting can be via access to the product team's issue tracking system, spreadsheets, documents, or email.
- A guide to your localization issue taxonomy. For more information, see [Issue taxonomy](issue-taxonomy.md).
- Instructions for reaching as much of the app UI as possible. You might be able to use your existing written test scenarios to aid the reviewer.
- A product team member who works side-by-side with the reviewer to walk them through the application. The reviewer brings language and cultural expertise. The product partner knows the workflows of the application and can quickly reach all areas of the product UI.
- If a working application can't be provided to the reviewer or some areas of the application are difficult to reach, the reviewer can work from screenshots. Screenshots are often available from the product's testing process or automation.

### Problems found by ICR

In addition to the linguistic aspects discussed under Linguistic validation, ICR can discover other important issues that might not be apparent when reviewing translated text in isolation.

- Untranslated text.
- Over-translated text.
- Mistranslation, possibly due to lack of contextual comments.
- Truncation: translated text that is cut off in the UI due to its length. Pseudolocalization finds many truncation issues, but it misses cases where a specific translation exceeds the growth factor supplied by pseudo.
- Clipping: Missing or partial characters due to characters that extend beyond the typical bounds. Examples include diacritics, stacked diacritics, and characters with long ascenders or descenders.
- Improper word wrapping, word selection, or line breaks.
- Mirroring issues.
- String concatenation or order-dependent insertions. Concatenation in the source can result in grammatically incorrect sentences.
- Improper pluralization for the language.
- Improper list forms for the language.
- Culturally inappropriate functionality.
- Missing locale-specific functionality. Examples include:
  - Missing sort by stroke order for Chinese.
  - Lack of local or international paper sizes for printing.
  - Lack of a way to represent the pronunciation of people's names.
- Problems with fonts or encoding.
- Incorrect sort order for the locale.
- Problems with the input or presentation of people's names.
- Problems with data formats. There can be issues with the presentation of numbers, dates, times, calendars, currency, addresses, telephone numbers, and so on.
