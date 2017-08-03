

# Establishing Localization Guidelines

High localization costs are incurred if the localization process is not run effectively. Establishing localization guidelines can increase the quality, accuracy, and user-friendliness of the international product version. Moreover, it can significantly reduce the cost of localizing your application into different languages. Establish clear guidelines for ensuring effective localization, for scheduling international releases, and for localization outsourcing.

### Ensuring Effective Localization

The initial product specifications should consider localization as part of the product cycle. Delaying localization to the end of the cycle can delay the shipping date because of any unexpected localization problems that require code changes. Localizability testing should start once the product functionality is stable. Localization for pilot languages or pseudo-localization should start once the software functionality is stable. Pilot-language localization is a good approach for large products that are localized in many target languages to speed up localizability code fixes. Localization for other languages should start once the UI is stable. A UI freeze is recommended before shipping, with enough time allotted so that the localization and user assistance (UA) teams can finish translating the software and Help files on time.

From a language standpoint, avoiding grammar and spelling mistakes in the original software text reduces the localization team's workload when those mistakes are corrected. Corrections will show up as a change to the localization team and will therefore need to be fixed again in the localized version. For the same reason, avoiding cosmetic changes in the content that do not add value to the meaning will speed up localization.

### Scheduling International Releases

The product-release schedule can differ from one market to another according to market needs. Ideally the localized product should be shipped on the same date as the original-language product, or with a delta less than 30 days. This concept is known as "simultaneous ship," or "sim ship." (For more information on sim shipping, see "[Understanding Internationalization](https://msdn.microsoft.com/en-us/library/bb688112.aspx)" and "[Designing a World-Ready Program](https://msdn.microsoft.com/en-us/goglobal/bb978435.aspx)"). However, shipping on the same day usually does not happen because localization, documentation printing, and package design continue after the original product has shipped. Figure 10-1 shows a typical time line for the development and shipping of a product. The product team and the international marketing team should decide what the delta between the shipping dates for the original product and the localized product should be. In **Figure 1**, Tier-1 languages refer to localized language versions that are shipped to the most important target markets; Tier-2 languages refer to language versions that ship to secondary markets, or are versions for which only a partial localization is planned. Localization for Tier-2 languages usually starts somewhere around the UI freeze of the original product.

![Localization timeline for international production](/media/hubs/globalization/IC155683.gif "Localization timeline for international production") 

**Figure 1** - Localization timeline for international production.

### Localization Outsourcing

Most of the time the product team does not have the language resources needed to translate the project to a targeted language. An external localization vendor is a good solution for this problem. It is important to provide localizers with the needed components to do their job. A localization kit is a subset of tools, source files, binary files, and other localization information that is handed off to localization vendors. The localization kit should contain everything that localizers need to finish their job correctly, such as the localizable file types and names from the original-language product, the target localization languages, the localization instructions, schedule details, translation style and glossaries, procedures for creating binaries using the localized resources, and contacts on the product team. (For more information on localization kits and on making translation easier for localizers, see "[Designing a World-Ready Program](https://msdn.microsoft.com/en-us/library/bb978435.aspx)").

By setting up communication channels between localizers and the appropriate people on the product team, you can speed up the localization process. Clear schedules of localization milestones make sure that the project will be delivered on time with high quality. The product team needs to make sure that their understanding of the overall internationalization process and of the localization process matches that of the localization team. For example, ensure that the text encoding used in localization is supported by the program. Localizers should be made aware of issues such as these from the outset.

The terminology that is going to be used in the translation process is based on localization glossaries; these glossaries should be reviewed before the translation process starts to make sure that the terminology suits the project objectives. Terminology within software games will differ dramatically from terminology used within financial spreadsheets, so glossaries should reflect these distinctions.

Keeping track of the words that are actually translated for each handoff is important in order to make sure that vendors are paid for the actual work done. The localized product can also be tested by a third party, preferably by native speakers of the target language. Finally, the localization manager needs to make sure that there is a good archiving system of all files that are sent to and received from vendors.

So far this chapter has dealt mainly with software localization, in which changes are made to a program's resources. The final section of this chapter examines the second component of localization: content localization. Like software localization, content localization presents its own challenges. However, there are some notable differences between the two.


