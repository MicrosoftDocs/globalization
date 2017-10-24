

# Element Resizing

The most time-consuming part of localizing the UI is resizing elements, particularly for applications that will ship in numerous languages and that contain a large number of dialog boxes. Therefore, it is recommended to use [Dynamic Layout](https://msdn.microsoft.com/en-us/library/bb514519(v=vs.110).aspx) where ever possible.

However, the following provides solutions for addressing this issue when working with Win32 dialog boxes.

You can minimize the amount of resizing necessary by creating your native-language dialog boxes with as much room to spare as you feel comfortable; extend text frames as far as possible so you can allow text to grow when it is translated. For example, in **Figure 1**, the frames surrounding the Name, Initials, and Mailing Address text fields extend all the way to the end of the edit control.

![Option dialog box with extended text frames](/media/hubs/globalization/IC60243.jpg "Option dialog box with extended text frames") 

**Figure 1:** Options dialog box with extended text frames.

Also, when possible, it is best to put text labels above UI controls such as edit boxes, as shown in **Figure 1**. This positioning allows for the greatest extension of the text field. Although putting text labels above UI controls is the best practice for localization, there are times when the text label is placed to the side of a control for a better look and feel. When this is the case, make sure to leave room for the text to expand in your design, and remember to extend the text field to cover all the space given. For instance, notice the extra space allotted between the text "Digit grouping symbol" and the list-box control in **Figure 2**. In **Figure 3**, you can see much of this extra space was used when the text was translated to German.

![Dialog box with extra space](/media/hubs/globalization/IC70081.jpg "Dialog box with extra space") 

**Figure 2** - Example of a dialog box for which extra space has been allotted between the text field and the list-box control.

![Text field can expand during translation](/media/hubs/globalization/IC136928.jpg "Text field can expand during translation") 

**Figure 3** - Example of how a text field can expand during translation.

When designing and localizing dialog boxes, you should test them with various screen sizes and resolutions to make sure they still look correct and fit on the screen, especially if your application allows the user to change the size of the application's dialog font. Microsoft Windows allows the user to scale the size of the system fonts, including fonts used for system-drawn items such as title bars and menus. (See **Figure 4**.)

![Advanced Appearance dialog box](/media/hubs/globalization/IC133190.jpg "Advanced Appearance dialog box") 

**Figure 4** - The Advanced Appearance dialog box from the desktop Display Properties property sheet, which allows you to change the font and font size of system items such as a menu.

The user can also resize system dialog boxes; the dialog controls will adjust simultaneously and automatically. (See **Figure 5**.) If you decide to incorporate this functionality into your design, carefully consider how your program will automatically adjust dialog boxes that have been localized-the ease with which the dialog box designs can be made to incorporate this feature is a good indication of how localizable they are.

For each localized dialog box, double-check that the order in which the user activates dialog elements via the Tab key still makes sense. If tabbing order isn't consistent, the localizer probably changed the relative position of dialog elements to make the translations fit, or the localizer might have set the coordinates of an item outside the coordinates of the dialog box itself.

![Find dialog box](/media/hubs/globalization/IC93133.jpg "Find dialog box") 

**Figure 5** - The Windows 95 Find: All Files dialog box. A user can adjust the width of the dialog box by dragging the border with the mouse.

To omit references to features not supported in a localized application, you could set the item's coordinates outside the dialog coordinates but, as mentioned, it is not assured that you'll have consistent tabbing order. Another way to omit references is to permanently dim such items. Although this practice preserves tabbing orders, it might confuse the user, who might not understand why certain commands are never available. As mentioned earlier, many applications have similar basic features. For example, most applications open and save files. Windows provides common dialog boxes for these operations (like the one shown in **Figure 6**).

![Common dialog box](/media/hubs/globalization/IC174355.jpg "Common dialog box") 

**Figure 6** - Example of a common dialog box.

Common dialog boxes have benefits for both the user and the developer. They make applications easy to learn because they provide consistency among applications. Such dialog boxes are also easy to implement because they require only a single API function call. Common dialog boxes do, however, present a dilemma for localized applications. Currently, each edition of Windows XP ships common dialog boxes only in the default language of that edition. An application that uses common dialog boxes will, therefore, always display them in the language of the system rather than in the language in use by the application. The mix will be jarring to a user who does not understand that some dialog boxes are drawn by the application and some are drawn by the system. Another problem for applications that use common dialog boxes is that they can be embedded within application-defined resources; the system dialog boxes might differ in size on different language versions of Windows-this can cause text to be clipped in applications.

While the configuration of Windows where your application runs might not provide common dialog resources in the language of your application, one way to work around this predicament is to use templates for the common dialog boxes instead of using the common dialog boxes themselves. The application can provide translated templates to the dynamic-link library (DLL) that contains the Windows procedures for the common dialog boxes. This method might work in the short term, but it does carry the risk that the translated templates will not be compatible with future versions of the common dialog boxes.

Controls, such as radio buttons and check boxes that allow the text to wrap are another way of handling text expansion. To allow multiple lines in a Win32 resource file, you can either manually add the BS\_MULTILINE property to the control (shown within bold in the following code):

```C++
CONTROL "Check1",IDC\_CHECK1,"Button",BS\_AUTOCHECKBOX |
&lt;B&gt;BS\_MULTILINE&lt;/B&gt; | WS\_TABSTOP,21,21,41,10
CONTROL "Radio1",IDC\_RADIO1,"Button",BS\_AUTORADIOBUTTON |
&lt;b&gt; BS\_MULTILINE&lt;/b&gt;,19,45,39,10
```
Or in Microsoft Visual Studio you can select the Multiline property in the particular control's property sheet. (See **Figure 7**.)

![Multiline property](/media/hubs/globalization/IC161976.jpg "Multiline property") 

**Figure 7**: Multiline property set in a Visual Studio control's property sheet.

In the .NET Framework, check boxes and radio buttons are automatically set for multiple lines. Allowing multiple lines is important since localizers might not have accessto these properties; their only alternative is to leave out information so they can fit the translation onto one line. **Figure 8** shows a dialog box that was well designed in the English-language version. When localized into German, however, the radio buttons' UI design was broken when the translated text was not allowed to wrap.

![Result of not allowing controls to wrap text](/media/hubs/globalization/IC5248.jpg "Result of not allowing controls to wrap text") 

**Figure 8**: Result of not allowing controls to wrap text.

Variables used in UI strings usually need extra space because you can never be sure how long the text will be that replaces the variable. A good rule is to add one line per variable in the text box so that there is enough space for the localized text. In **Figure 9** the translation of the first sentence "Welcome to the %s Registration wizard." will require the entire first line. Thus the inserted text of the variable will extend the sentence onto a second line.

![Allowing one line per variable in a text box](/media/hubs/globalization/IC110523.jpg "Allowing one line per variable in a text box") 

**Figure 9:** Example of allowing one line per variable in a text box.

The basic rule is that you should leave about 30 percent additional room for text expansion. Most of the time this practice works. The only exception is when you have a string or button that has less than 10 characters. Take, for example, the following OK button.

![OK button](/media/hubs/globalization/IC6685.gif "OK button") 

If you followed the 30-percent rule, all you would do is leave space for one more character; but this does not hold true if you are localizing the text into Spanish. The verb for "accept" in Spanish is "aceptar" (which is used within the UI to mean "OK"). However, the word "aceptar" is 250 percent bigger than the original text.

![Spanish Accept](/media/hubs/globalization/IC16861.gif "Spanish Accept") 

Therefore, the exception to the 30-percent rule is if the text has less than 10 characters, leave room for at least 400 percent growth. Remember that these are general rules, and all languages' UIs should be designed to look as good as possible, even in English. However, the best guideline is to leave as much space for text expansion as possible. Minimizing the need for resizing is a vital part of making sure that Web pages are localizable also.


