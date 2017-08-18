

# Isolate Localizable Resources

## Overview and Description

Once you know what you are looking for, it is easy to identify source code that isn't properly set up for localization. The most extreme cases are populated with hard-coded strings, constants, and characters. Files containing hard-coded localizable elements are the biggest nightmare to deal with. Translators cannot easily translate the source-code files, especially if the code is continually evolving. Many translators are not programmers and might delete important details, such as closing quotation marks or semicolons, or they might translate programming keywords as well as strings. Then developers must take time to clean up these files so that they will compile correctly. Hard-coded elements are difficult to find because they do not show up until the software is localized. Figures 1 and 2 show some common problems that occur during localization.

![Hard-coded string example 1](/media/hubs/globalization/IC150997.jpg "Hard-coded string example 1")

**Figure 1:** The string "Unknown Modem" was hard-coded and thus went untranslated.

![Hard-coded period](/media/hubs/globalization/IC35490.jpg "Hard-coded period")

**Figure 2:** The string is a text resource without a period at the end of sentence, and the period was hard-coded.

Any translator would assume that the lack of punctuation in the previous figure is a mistake and would end the translated sentence with a period. Thus the localized version ends up with two periods.

Separating all localizable items into one or more files makes localization much easier to manage. The following list shows the major program elements that require localization.

**Major program elements requiring localization:**

-   Menus
-   Messages
-   Dialog boxes
-   Prompts
-   Images
-   Sounds
-   Toolbars
-   Status bars
-   Constants

## Solution

One approach would be to create a complex process that strips out all localizable items from source files and that reincorporates these items once they have been translated. That way, you could declare strings in the same area as the code that uses them. However, designing and implementing such a scheme hardly seems worth the effort when better localization methods are available. An alternative approach would be to place all strings and constants in header files, but then you would have to recompile any source files that included translated headers.

By far the simplest and most straightforward method of dealing with localizable resources is to put everything in some type of resource repository such as Windows resource files, .NET assembly files, or a database when dealing with Web content. Resource repositories, which will be described in more detail later in this section, tend to be easy to edit, and they eliminate the need for recompiling source code. Because of these advantages, developers have used resource repositories as a spot to store resources referenced in one or more places in their code. This actually adds complexity to what from a localization perspective should be a resource file containing only resources that need localization. Resource repositories have the following resources:

-   **UI resources.** These can be localized in an arbitrary way without any loss of functionality.
-   **Resources used for the adaptation of a product (font and locale information, folder names, account names, and so on).** These strings need to be localized according to certain rules; incorrect localization has functional impact. If possible, these resources should be queried from the supporting platform and not stored within the application.
-   **Debug resources.** These shouldn't be localized, but there is no loss of functionality if they are.
-   **Functional resources (registry keys, function calls, strings communicated between components, and so on).** These strings can't be localized without loss of functionality.

To complicate things further, there are also resources that don't fall clearly under just one category (for example, functional text that is being displayed in the UI, or UI strings that have to be localized in a certain way so that they don't break the product). This is a huge challenge for localization because there is no way to tell what category a resource belongs to without looking at the code. Since localizers generally don't have access to the code (and many don't understand the code anyhow), they are depending on their own judgment. As a result, they introduce many defects that are costly to detect and address.

The goal is to separate the first two categories (UI resources and resources used for product adaptation) from the last two categories (debug resources and functional resources) and to make sure that resources clearly belong to one category only. Since localizers usually don't have access to registry keys, it is best if you keep all text out of them and store the text strings in your localizable resource. To further reduce complexity and to increase flexibility of the code, you should keep the category of resources used for the adaptation of a product as small as possible. For example, instead of using multiple instances of strings that need to be localized identically (like folder names and account names), refer to one instance of this string only.

Although moving localizable items like strings and icons into resource repositories is a good localizability practice, it is important to emphasize that just like anything that is good, sometimes more is way too much. Just because one chocolate bar tastes good, eating 10 at one sitting can leave you with some undesirable consequences. This goes for resource files also. As mentioned earlier, there are four distinct localizable categories for resources. One of the most counterproductive practices is putting all of your resources (including items that do not need to be localized) together in one place, rather than separating them into different resource files by categories. This practice can confuse localizers, causing two major problems to occur:

-   The unnecessary translation of resources in general (which wastes money that could be used elsewhere).
-   The inadvertent translation of resource names that are specific or necessary to your application. (One example includes a command string like "Open" that your code does not recognize anymore because it has been translated to "Ouvrir" in French. Another example is translating the name of a mutex or event that an application is checking for in the source language.)
-   Also, you should not expect services and system components to always be in English, since they might have been translated for localized versions. For instance, the following code will fail when run on a localized version because all values in bold are translated on localized systems!

```C++
// user is system, which means cannot log on
if ( (_tcscmp(lpBuffer,TEXT("SYSTEM")) == 0) ||
 (_tcscmp(lpBuffer,TEXT("LOCAL SERVICE")) == 0) ||
 (_tcscmp(lpBuffer,TEXT("NETWORK SERVICE")) == 0)
```

A better way to handle resources that come from localizable platforms is to use application programming interface (API) calls to get the system's localized values. The following example uses *SHGetFolderPath*, which will return the correct localized version of the path from one localized system to another localized system. (For information on the different Shell calls, see the [Shell Programmers Guide](https://msdn.microsoft.com/en-us/library/bb776778.aspx).)

```C++
TCHAR szPath[MAX_PATH];
SHGetFolderPath(NULL, CSIDL_PERSONAL, NULL, 0, szPath);
```

A good practice is to put resources that do not need localization into header files (like .H files for the C programming language). This gives you all the necessary flexibility of a resource file, and yet these resources will never get confused with localizable resources. Also, if the technology you are working with does not have some way to separate localizable resources, use whatever feature it does have that will ease the localizer's job. Always keep in mind that you should group non-localizable items separately from localizable items.

Another good practice when working with resources is to not change resource identifiers. Most resource repository systems have some index the code can use to access the string or other item needed for creating the UI. It is the use of this index that makes resource files great choices for localization. By merely changing the repository from one filled with the original language to one that contains the new language, the index now points to the correct language.

This action is not without peril. Suppose that during an update process you decide that you need to change a resource identifier (leaving the text in the resource unchanged). By doing this, you have now made your translated resource repository unusable for your update because your code expects the text to be located somewhere else in the repository. Consequently, if you do nothing, you might get the wrong text. To avoid this, you would have to go in and change your translated resource by at least moving the old translation to the new location or by doing the translation all over again. The latter is contrary to the guiding principle of keeping required translations to a minimum.

When dealing with resource repositories, you will save a lot of money if you remove unused strings and dialog boxes before having the resources localized. Translators and localizers have no way of knowing which of your strings are used and which are not. Thus all they do is what you tell them (such as to translate a particular resource file). For example, suppose one out of every 50 strings in your resources is not used. Referring back to the 25,000-string project, that means there are 500 strings in the resources that do not need to be translated. If you have 20 languages costing 42 cents per string to localize, those 500 strings end up using $4,200 of your budget-money that could have been allocated elsewhere.


