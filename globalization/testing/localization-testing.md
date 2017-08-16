---
title: Localization Testing
description: Localization testing will test the UI is localized to the correct languages. This is done after globalization test is complete.
ms.assetid: fe7e19f0-864c-4ba0-b05e-349c566dc061
ms.date: 03/16/2016
---

# Localization Testing

Although localization and, by extension, localization testing are not strictly a part of the development of world-ready software, localization becomes possible once you have developed world-ready software. If you do decide to localize, you should be familiar with the scope and purpose of localization testing. Localizers translate the product UI and sometimes change some initial settings to adapt the product to a particular local market. This definitely reduces the "world-readiness" of the application. That is, a globalized application whose UI and documentation are translated into a language spoken in one country will retain its functionality. However, the application will become less usable in the countries where that language is not spoken.

Localization testing checks how well the build has been translated into a particular target language. This test is based on the results of globalized testing where the functional support for that particular locale has already been verified. If the product is not globalized enough to support a given language, you probably will not try to localize it into that language in the first place!

You should be aware that pseudo-localization, which was discussed earlier, does not completely eliminate the need for functionality testing of a localized application. When you test for localizability before you localize, the chances of having serious functional problems due to localization are slim. However, you still have to check that the application you're shipping to a particular market really works. Now you can do it in less time and with fewer resources. The following section shows you some of the general areas on which to focus when performing a localization test. (For information on more specific areas, see "Localization Testing of the UI" later in this article.)

**[General Areas of Focus in Localization Testing]**

Localization testing should focus on several general areas. The first involves things that are often altered during localization, such as the UI and content files. The second consists of culture-specific, language-specific, and country-specific areas. Examples include configurable components-such as region defaults and the default language-as well as language-specific and region-specific functionality-such as default spelling checkers, speech engines, and so on. You should also test the availability of drivers for local hardware and look for the encryption algorithms incorporated into the application. The rules and regulations for distribution of cryptographic software differ from country to country.

Pay specific attention to the customization that could not be automated through the globalization services infrastructure (Win32 NLS APIs and the .NET Framework). For example, check that formatting of mailing addresses is locale-specific and that parts of the user's name are ordered correctly. (The order in which surname and first name appear varies according to country. For instance, some Muslim countries and certain regions in India use a different name order than that used in the English language.) Functionality of this kind is often implemented by an application-testing must verify its correctness.

Other areas of localization testing should include basic functionality tests; setup, upgrade, and uninstall tests that are run in the localized environment; and, finally, application and hardware compatibility tests that are planned according to the product's target market.

**Platform in Localization Testing**

Any language version of Windows XP or Windows 2000 can be selected as a platform for the test if the product is properly globalized. Of course, in the case of localization testing, the localized version of the operating system can be a wise choice, since that's the most likely environment for your application in the real world. However, a globalized and localizable application, even after it undergoes localization, must be able to run on any language version of the operating system and with MUI installed.

You should run the application with MUI installed when your application implements an MUI behavior, through pluggable UI, satellite dynamic-link libraries (DLLs), or some other technique that adjusts the UI language to the user's preferences. MUI allows the user to switch the UI language of the operating system and thus you must make sure your application matches the operating-system settings. You should verify the behavior of the application when the user's default language of the UI differs from the other locale settings. By doing so, you'll immediately see any problems in the way resources are loaded and processed.

**Localization Testing of the UI**

Also keep an eye on the behavior of applications that run processes in a system-such as operating-system services-rather than in a user's context. When a system process queries its user default UI language settings, it might get a result different from what a user's process running at the same time will get. This can cause localization problems, inconsistency in the UI that the user sees (if parts of it are generated by the system services), or even problems in functionality. In order to avoid those problems, always check an application's behavior with different default user and system UI languages. The settings for UI languages should also be different from those used in the development environment.

For example, assume you have a machine with MUI installed and a user whose default UI language is different from that of the system. Suppose a fax service waiting for incoming calls is running continuously and that, when a fax arrives, the service displays a notification message to the currently logged user (if there is one). You must ensure that the message be in the user's language, which might not necessarily be the same as the one returned to the fax service when it queries its default UI language.

In particular, localization testing of the UI and linguistics should cover items such as:

-   Validation of all application resources.
-   Verification of linguistic accuracy and resource attributes.
-   Checking for typographical errors.
-   Checking that printed documentation, online Help, messages, interface resources, and command-key sequences are consistent with each other. If you have shipped localized versions of your product before, make sure that the translation is consistent with the earlier released versions.
-   Confirmation of adherence to system, input, and display environment standards.
-   Checking usability of the UI.
-   Assessment of cultural appropriateness.
-   Checking for politically sensitive content.
-   Making sure the market-specific information about your company, such as contact information or local product-support phone numbers, is updated.

It's also a good idea to check that everything you are going to distribute in a local market complies with the local laws and regulations. (See Designing a World-Ready Program.) This includes not only the license agreement but also online Help and other user documentation.

You've now seen the importance of globalized testing, localizability testing, and localization testing in terms of ensuring both that a product is world-ready and that it is suitable for worldwide distribution. One way in which the testing process has changed to reflect new goals involves the type of tools currently being used.


