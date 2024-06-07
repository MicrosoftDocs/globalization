---
title: How to perform localization testing
description: Defining a process for localization testing, identifying tools that can help with testing, and creating test data help ensure that testing identifies issues.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 05/04/2024

---

# How to perform localization testing

This article discusses the methods for testing your localized products. It assumes that you have already planned for [when](when-to-perform-internationalization-testing.md) and [how](how-to-perform-internationalization-testing.md) the validation of other aspects of internationalization is done. Internationalization testing is typically a prerequisite to effective localization testing.

Test tools are discussed in [Why international validation is important](why-international-validation-is-important.md#test-tools). If your automated test has been well globalized, running automated test cases on all localized versions is an efficient way to test functional parity across languages. If you do not have full automated test coverage, plan for manual validation.

Some automated test frameworks are able to detect and report visual issues such as bad layout, but having someone conduct a visual sanity check is a good alternative.

## Localization testing

Localization testing checks how well your product is translated into a particular target language and confirms that there are no visual or functional issues. Ideally, [internationalization testing](when-to-perform-internationalization-testing.md) has already uncovered most visual and functional issues that could impact localized versions, and these have been addressed before localization testing.

Localization testing is often broken down into several sub-areas, based on the tools and skills required to perform the validation:

- Functional validation (verify functional parity across language versions)
- [Visual validation](#visual-validation) (verify that all parts are fully localized, there are no cosmetic defects, and visuals are culturally appropriate and not political sensitive)
- [Linguistic validation](#linguistic-validation) (verify linguistic accuracy, as well as cultural appropriateness and political sensitivity of the text)
- [Other risk areas](#other-risk-areas) (market specific features, audiovisual content, speech input/output, legal compliance, ability to reach local contacts for sales or support, and so on)

### Visual validation

Localization testing for your product’s UI and language-related items should:

- Validate all application resources, including strings and translated images.
- Check that printed documentation, online help, messages, interface resources, and keyboard shortcuts are consistent with each other. If you have shipped localized versions of your product before, make sure that the translation is consistent with the earlier released versions.
- Confirm adherence to system, input, and display environment standards.
- Check the usability of the UI.
- Assess cultural appropriateness.
- Check for politically sensitive content.
- Ensure the market-specific information about your company, such as contact information or local product-support phone numbers, is correct.

### Other risk areas

The second major focus consists of culture-specific, language-specific, and country- or region-specific areas. Examples include configurable components such as region defaults and the default language, as well as language-specific and region- or market-specific functionality, for example, spelling checkers and speech engines. You should also test the availability of drivers for local hardware.

Pay specific attention to customization that couldn't be automated using the infrastructure provided by your platform or language globalization services. For example, check that the formatting of mailing addresses matches the locale conventions.

You also need to check that everything you're going to release to a new target market complies with the local laws and regulations. This includes not only the license agreement but also any user documentation. The use of encryption   can be regulated in certain regions, so check that it's used in conformance to local regulations.

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

### In-context review

In-context review (ICR) can be the key to ensuring a high quality localized and translated experience for international users. ICR means performing [linguistic validation](#linguistic-validation) in the context of the running application. For documentation, the reviewer uses the same presentation medium that end users see. Performing linguistic validation in the context of the user's experience catches more problems than doing it at the resource level.

The criteria for choosing in-context reviewers are the same as for [linguistic validation](#linguistic-validation). The reviewers should be provided with the following resources:

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
