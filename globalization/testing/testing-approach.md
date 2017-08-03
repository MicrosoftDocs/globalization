

# Globalization Testing Approach

In order to help you verify that a product's functionality has been globalized, some central ideas of globalization are restated here. Among these ideas, an application or a component is considered globalized if:

-   It is Unicode-based; that is, any Unicode text can be handled successfully.
-   Correct encodings are selected for text conversions, if conversion is needed to interact with legacy systems.
-   The code follows the user's culture-specific settings.

Whenever a piece of code handles text or deals with locale-sensitive functionality, it has to be tested for proper functionality from the perspective of world-readiness. Code that has been globalized can process data (text) in multiple scripts and can adjust itself to the environment (in terms of language settings, for instance). Verifying functionality can be planned as a separate test pass, but it is better to fit it into regular functional testing.

Practical guidelines for globalization of your test go beyond breaking the code-page dependency in the test data and checking the cultural accuracy (which means matching the user's language settings). To make testing more effective in searching for globalization bugs, target specific functionality and create an environment where this functionality is likely to break. Here are some of the areas of functionality that testers should verify:

-   Input, store, process, and output multilingual text with no data loss.
-   Display UI element so script properties are respected. This includes mirroring and text rendering.
-   Proper handling of language settings such as date, time, number and currency formatting, calendar and sorting settings.

You've seen the importance of globalizing your test as well as particular areas of functionality in which to search for globalization bugs. How do you now go about preparing a globalized test?

Before testing is performed, there are several items to consider in preparation. For example, you'll need to determine priority levels for components that are going to be tested, choose a test platform, and create a proper testing environment.


