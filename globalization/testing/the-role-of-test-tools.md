---
title: The Role of Test Tools
description: Using automated test tools is an effective way to verify the functionality of localized products or to test the degree of a product's globalization.
ms.assetid: c991a0f2-6712-40b8-b5e2-b1fcc0c377de
ms.date: 04/05/2017
---

# The Role of Test Tools

Test tools play an essential role in today's testing process, particularly those that are automated. While automated testing cannot replace manual testing completely, many test areas gain tremendous benefits from its introduction. For instance, using automated test tools is an effective way to verify the functionality of localized products or to test the degree of a product's globalization.

By running automated tests on the original and localized applications, side by side, you can verify that localization of the application does not break the functionality. Furthermore, with automation you do not need to understand the language of the localized UI since the tools can test the functionality regardless of the UI language. (For instance, "Click the default button"—where the word "default" in this case is used in the generic sense-is a test of functionality that can work for any language.) In addition, ensuring that a product is globalized requires the ranges of test input to be extended and environment settings to be more diverse during the test than was the case before creating world-ready software. Automation makes it easier to deal with this increase in the volume of test cases and allows you to efficiently track the results of the globalized test. Restoring the locale settings or test input that brought about a failure in a program also becomes easier.

Automation of test runs, however, involves more than just running old, trusty test tools on your new product under a globalized environment. Test tools that check functionality of an application's UI can be broken when the tested application is translated. Even when not affected by translation, test results may be incorrect if the tool verifies dates, for example, and assumes that the date format is fixed. (Of course, in globalized applications, the date format varies according to locale and region. See "[Using Locale Model](https://msdn.microsoft.com/globalization/mt662310)".) The inability to use international test data can also make a test tool unusable.

In order to avoid these and similar problems, developers of test tools must follow the same rules as the developers of globalized software do. Test tools must be globalized, must adjust themselves dynamically to locale settings, and should be able to process international text data. Also, if they have to access localizable objects by name, test tools must be localizable (which in this case means they need to allow for easy translation of UI elements).

At Microsoft, test tools and techniques vary from one team to the next. Experience shows that some tools are easier to globalize, while others are not. More advanced programming models usually provide better ways to make the code universal in regard to locale and language settings.

Test tools written in C++ to test the operating system APIs rarely are dependent upon language settings; if they are, those dependencies can be easily broken. Scripts accessing the UI of the tested applications through Component Object Model (COM) Automation interfaces are rarely broken due to localization of the UI.

The programming systems that are known to be problematic in globalized testing are generally built on non-standard APIs and are thus unable to handle multilingual text. Or the systems might lack the ability to query the language settings and to format the output accordingly. Finally, systems that access the UI elements by their names can also be problematic in terms of globalized testing.

Therefore, if you base your automation testing on an older tool with a few or all of the limitations just listed, some of the steps required for globalization of the test might not be possible with your automation. First, try to substitute this test with a manual test. Second, try to make the tool useful for multilingual testing by doing the following:

-   Refer to UI elements by their resource identifiers, ordinal numbers, or window classes, not by the caption. Captions are hard to track with multilingual development.
-   Isolate text resources from the code in a way that's easy to localize. For example, they can be an include file defining text constants. As a result, localizers will be able to translate the external "resource file," and your tool will run with a localized UI.


