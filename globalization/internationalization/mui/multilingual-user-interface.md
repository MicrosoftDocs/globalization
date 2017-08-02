This documentation is archived and is not being maintained.

# Multilingual User Interface

### **Overview of MUI**

**Multilingual User Interface (MUI)** is a Microsoft technology that provides users the localized user interface for the internationalized applications and user interface language resource management in the Microsoft Windows OS. MUI has been supported on all versions of Microsoft Windows since Windows 2000, but MUI was mainly an add-on until Windows Vista. Windows Vista and later Windows releases were designed to be neutral-core operating system, which enables the developers to take advantage of the MUI mechanisms for the app development without creating customized logic for resource handling and language management.

MUI allows large corporations to roll out, support, and maintain the same worldwide image with a single installation. Other benefits of MUI are that users of different languages can share the same workstation, and roaming users can take their localized UI from one workstation to another. For instance, one user might choose to see system menus, dialog boxes, and other text in Japanese, while another user logging onto the same system might prefer to see the corresponding text in Danish.

A Windows system with MUI set to a particular UI language will largely look and behave like the localized version, with some exceptions. Since MUI runs on top of the English version of Windows, from a feature and architectural point of view, localized versions of Windows are the same as the MUI version on English Windows. However, on localized versions:

-   The UI resources are fully localized.
-   Windows Setup information—such as the system locale, user locale, and keyboard layout—is customized for the specific language or country. With the MUI Pack, however, this is a policy setting. By default, installing MUI does not change locale settings of the English system where it is installed.
-   Additional country-specific printer drivers are added in the East Asian versions only.

The advantages for using the MUI technology include:

-   Simplified language management for software localization. MUI allows the language settings for the operating system to be changed to a supported language according to user preferences.
-   An innovative resource technology based on the splitting of the application code binary from language resource files. You can add resources for an additional language without needing to recompile or relink your application. Additional localized resources become optional add-ins.
-   Complete application programming interface (API). Windows Vista and later expose the MUI API for you to use in adding MUI functionality to globalized applications. Language management functions enable your applications to support a wide variety of user interface languages. The API also includes resource loading functions that enable the resource loader to load resources on Windows Vista and later, as well as pre-Windows Vista operating systems.

### Core Concepts of MUI

The fundamental idea behind MUI is to **separate the storage of localizable resources from application source code**, so as to be able to architect any multilingual application as a combination of a language-neutral core binary and a set of language-specific localized resource files.

Once application source code is stored separately from the localized resources, it becomes easy to dynamically load the appropriate localized resources for a given application context based on a logic that takes into account system, user and application-level settings for the user interface language.

These fundamental attributes of MUI help facilitate business scenarios such as:

-   An improved localization model for user interface and help content, via the physical separation of application source code and localizable resources.
-   Treating the localizable resources as dynamic content and loading them according to the UI language settings and fallback preferences. This enables scenarios such as:
    -   Switching from one UI language to another one at run-time.
    -   Creating regional or worldwide single deployment images that cover a set of languages for OEMs and enterprises.

See more information at [MUI Fundamental Concepts Explained](https://msdn.microsoft.com/en-us/library/windows/desktop/ee264324(v=vs.85).aspx).

### MUI in Win32

The number of possible ways to implement an MUI solution in applications is endless, but each possibility is a variation of the same basic idea: create a language neutral functional binary and one satellite resource DLL per target language.

Assuming that you have already separated your resources from your core functional language binary, creating an MUI solution is as easy as following these basic steps:

-   Detect the UI language of the operating system.
-   Enumerate all languages for which you have a localized satellite DLL.
-   Load the appropriate satellite DLL that matches the UI of the operating system.
-   Allow the user to select a different language for your application, if you don't offer a localized solution for that particular language.

Before examining the technical implementation of MUI in Win32 applications, it is important to underscore that the only safe assumption for a fallback language is the UI language of the operating system. If you do not offer a localized solution for that language, then instead of defaulting to a given language (such as English), you will need to enable the user to select a language. For example, if the UI of the operating system is set to French, and yet you don't have localized files for French, you might be tempted to default to English resource files. This might be an accepted solution in Canada, where French and English coexist. But if a French user lives in Belgium, for example, odds are that his or her second language is Dutch rather than English.

**Additional information** can be found at:

-   [Using Multilingual User Interface](https://msdn.microsoft.com/en-us/library/windows/desktop/dd374113(v=vs.85).aspx) 
-   [Resource Handling in the .NET Framework](https://msdn.microsoft.com/en-US/library/mt670612) 
-   [Multilingual content in Web Pages](https://msdn.microsoft.com/en-US/library/mt670613) 

[Show:]{} Inherited Protected
