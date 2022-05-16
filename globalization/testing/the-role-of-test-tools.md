---
title: The role of test tools
description: Using automated test tools is an effective way to verify the functionality of localized products or to test the degree of a product's globalization.
---

# The role of test tools

Test tools play an essential role in the testing process, particularly those that are automated.
While automated testing can't completely replace manual testing, many test areas gain tremendous benefits from automation.
For instance, using automated test tools is an effective way to verify the functionality of a localized product.
Automated tests can validate the degree of a product's globalization.

Running automated tests on the original and localized applications side by side can verify that localization of the application doesn't break functionality.
With automation, you don't need to understand the language of the localized user interface since the tools can test the functionality regardless of the language.
For instance, "Click the default button" is a test of functionality that can work for any language.
Ensuring that a product is globalized requires the ranges of test input to be extended, and environment settings to be more diverse.
Automation makes it easier to deal with this increase in the volume of test cases and allows you to efficiently track the results.
Restoring the locale settings or test input that brought about a failure in a program also becomes easier.

Automation of test runs involves more than just running old, trusty test tools on your new product under a globalized environment.
Test tools that check functionality of an application's UI can be broken when the tested application is translated.
Even when not affected by translation, test results may be incorrect if the tool verifies locale-formatted data, and assumes that the data format is fixed.
In globalized applications, the date format varies according to locale and region.
See [Locale and culture](../locale/locale-and-culture.md).)
The inability to use international test data can also make a test tool unusable.

In order to avoid these and similar problems, developers of test tools must follow the same rules as the developers of globalized software do.
Test tools must be globalized, adjust themselves dynamically to locale settings, and process international text data.
If they have to access localizable objects by name, the test tools must also be localized.

Experience shows that some tools are easy to globalize, while others aren't.
More advanced programming models usually provide better ways to make the code universal in regard to locale and language settings.

The programming systems that are known to be problematic in globalized testing are built on non-standard APIs and are thus unable to handle multilingual text.
Or the systems might lack the ability to query the language settings and to format the output accordingly.
Finally, systems that access the UI elements by their names can also be challenging.

If you base automated testing on an older tool with a few or all of the limitations listed, some of the steps required for globalization of the test might not be possible.
First, try to substitute this test with a manual test.
Second, try to make the tool useful for multilingual testing:

- Refer to user interface elements by their resource identifiers, ordinal numbers, or window classes, not by the localized caption.
  Captions are hard to track with multilingual development.

- Isolate resources from the code in a way that's easy to localize.
  For example, they can be an include file defining text constants.
  As a result, translators will be able to translate the external resource file, and your tool will run with a localized UI.
