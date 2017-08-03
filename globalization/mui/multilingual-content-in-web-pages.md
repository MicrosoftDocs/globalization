

# Multilingual content in Web Pages

Offering Web sites that provide content in the user's preferred language follows the same principles as providing multilingual content for Win32 applications:

-   Store your translatable resources in a database, in XML, or in resource files.
-   Reference string resources by variables.
-   Detect the display language at initialization time.
-   Load appropriate resources at display time.

Dynamic generation of language-specific Web interfaces from XML data is not hard-at least, it is not any harder than using XML to store UI data for a single language. The traditional model is to create an XML file containing all necessary data, bind the XML data to an HTML object on the page or apply an XSL transformation-and that's it! The client gets a nicely formatted page and your data, which is isolated from the code and UI, is easy to maintain. A multilingual scenario does not require much change to this traditional model. You will basically need to replace one single-language XML file with a set of language-specific files, which are loaded according to the settings of the client. An important step in building a UI according to the user's preferences is getting those preferences in the first place. There are several methods you can use:

-   Use [window.navigator.browserLanguage](https://msdn.microsoft.com/en-us/library/ms533542.aspx) to check the language of the browser (for the UI language) and use [window.navigator.userLanguage](https://msdn.microsoft.com/en-us/library/aa918377.aspx) to check the language of the user (for cultural preferences). Query the values in a client-side script and post them to the server for a server-side UI construction.
-   Provide the user with a list of available languages and send (post) user feedback to the server. This solution can be combined with the next one.
-   Query the user's profile. You can use this method if the user is authenticated.
-   Query the value of HTTP\_ACCEPT\_LANGUAGE to find out what languages the browser accepts. If the browser accepts multiple languages, you can choose whatever language your resources happen to be in, obviously selecting from the preferred languages first.

The advantage of the last two methods is that you can use them at a session's initialization step—for example, in the *Session\_OnStart* procedure of *Global.asa.* However, these two solutions might be less flexible than the first method, in which you query values in a client-side script. In effect, the last two methods are equivalent to making an educated guess about the user's preferred language. Suppose the browser language is set to Finnish and your Web pages are not available in that language. You might default to English, not realizing that the user's second language is Russian, not English. Furthermore, there is not much advantage to the last two methods if their *Session* object is disabled in the first place.

Rather than selecting one particular algorithm as the preferred solution for all scenarios, it is wiser to base your solution upon the specific business case at hand. As you will see in the the sample code that follows, the decision on which language to use to display content is isolated within the *GetSessionLanguage()* function. In order to make *GetSessionLanguage()* universal, the function returns the language ID. However, it would be better to set the *Session's* UI language variable. As a general rule, you should set a language for each user's session. This way you allow different languages for different users, and you can confine your decision about which UI language to a single instance—within the initialization code. Some applications might avoid using *Session* states, in which case a language ID returned as a string comes in handy. Note also that *GetSessionLanguage* cannot be made completely universal; it will depend on the naming conventions you adopt for the XML files in your product, the set of languages you have localized into, and the default language of your application. The following code illustrates one mechanism possible for dynamic construction of a language-specific UI. To make things more general, it is not specified whether the code is executed in a *Global.asa* initialization of a session or later. Error handling was also removed from the code, but you should be able to handle errors that might arise, such as when the XML file for a particular language cannot be found.

Partial sample VBScript code:

``` {style="FONT-FAMILY: Consolas, Courier, monospace" xmlns=""}
<%@LANGUAGE = VBScript %>
<%
' Function GetSessionLanguage() is omitted for simplicity. It
' would be application-specific anyway. You can find a sample of
' this type of function in the Samples\MultiLanguageWeb\
' BrowserSniff subdirectory on the companion CD. The function
' implements language detection based on the value of
' HTTP_ACCEPT_LANGUAGE.
' It is assumed that the function returns a language ID string
' that is never empty.
' The default language of the site is returned if the language
' of the user's choice is not available.' InitializeUI() detects the language to be loaded,
' stores the language ID in a session variable,
' loads the proper resource XML file and
' language-independent XSL template,
' generates the UI, and writes it to the client.Sub InitializeUI()
'Returns a non-empty string
Session("ui_language") = GetSessionLanguage()
' If your languages canot be presented in one code page, you
' can set the Session.Codepage and Response.Charset values
' here, based on the language.
' But always handling text in UTF-8 might be a better solution.
Session.Codepage = 65001
Response.Charset = 65001
Set Session("xmlData") = Server.CreateObject("Msxml.DOMDocument")
Set Session("xmlStyle") = Server.CreateObject("Msxml.DOMDocument")
Session("xmlData").load(Server.MapPath("xml/"&Session("ui_language")&"/uiRes.xml"))
Session("xmlStyle").load(Server.MapPath("xml/uiTemplate.xsl"))
Response.Write(Session("xmlData").transformNode(Session("xmlStyle")))
End Sub
...
%>
```

The XML file can contain all the information needed for on-the-fly generation of localized content. If you need to apply directionality to your localized pages, use language-specific graphics or URLs. In the previous code sample, if English, French, German, and Japanese resources are defined, the structure of the "resource" tree looks like the one shown in **Figure 1** below.

The assumption is that the same information is kept in each language version of the XML resources, thus preserving the same schema among the languages. With this model you can use the same XSL transformation on all of the files, which will simplify your code. Adding new language resources becomes easy as well.

![Structure of the resource tree](/media/hubs/globalization/IC856183.png "Structure of the resource tree")

**Figure 1:** Structure of the resource tree


