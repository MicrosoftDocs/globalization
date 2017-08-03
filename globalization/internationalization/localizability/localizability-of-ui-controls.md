

# Localizability of UI Controls

In addition to element resizing, another major localizability consideration for the UI involves UI controls. Since programmers do not have to create their own controls, such as list views and edit boxes, their job is made somewhat easier. However, when used in certain ways, these same controls can pose a problem for localizers. Edit boxes, for instance, often need to be repositioned depending on the syntax of the target language. The following sections will give you some tips on what to be aware of when working with UI controls.

### UI Controls Within Sentences

The biggest problem with UI controls in terms of localizability is when programmers use them as part of a sentence. Localizers often have to either change the position of the controls (if they have access to a formatting tool) or settle for an improper sentence structure. For example, **Figure 1** is designed with an edit control in the middle of a sentence. In its German localization, the edit control had to be repositioned so that what it represented could fit syntactically in the German translation. (See **Figure 2.**)

![This edit control occurs in the middle of a sentence.](/media/hubs/globalization/IC156390.gif "This edit control occurs in the middle of a sentence.") 

**Figure 1:** This edit control occurs in the middle of a sentence.

![When localized into German, the edit control had to be repositioned](/media/hubs/globalization/IC165327.gif "When localized into German, the edit control had to be repositioned") 

**Figure 2:** When localized into German, the edit control had to be repositioned.

A better design is to rethink the whole phrase, so that the edit box can be removed from the sentence, so the localizer does not have to reposition the edit box. (See **Figure 3.**)

![When localized into German, there is no need to reposition the edit control.](/media/hubs/globalization/IC156091.gif "When localized into German, there is no need to reposition the edit control.")

**Figure 3:** When localized into German, there is no need to reposition the edit control.

The other problem with using UI controls in sentences is when you have a drop-down box. As mentioned earlier, strings built at run time cause problems because of grammatical differences (such as the existence of gender in some languages) and syntactic differences (such as verbs that can either precede or follow a noun depending on the language and context). Similarly, drop-down boxes might have terms in them that could change the translation of the sentence depending on the term selected. Plus, moving and aligning drop-down combo boxes that usually consist of multiple controls is always error-prone.

### Hidden or Overlapped UI Controls

UI controls such as buttons or drop-down lists should not be placed on top of other controls. Some localization tools are not able to change the state of a dialog box; thus the localizers might not even know that there are hidden controls to translate. Even when localizers have access to all the controls, sizing and hot-key issues with hidden controls are usually only found through testing. In Figure 16, the UI is not localizable because the button size cannot be extended to the length required for the translation without rearranging the button positions; also, rearranging is not possible because there is not enough space in the dialog box. Although rearranging button positions is costly and makes the UI inconsistent among languages, there might be times when it is necessary to do so.

![dialog box is not localizable](/media/hubs/globalization/IC18806.gif "dialog box is not localizable") 

**Figure 4:** This dialog box is not localizable because the button size cannot be extended without rearranging the position of the buttons, and there is not enough space for rearrangement.

**Figure 5** demonstrates the other problem with hidden controls. Even if there were room for the expansion of the Edit Properties button, unless the Accept button is resized also, the Edit Properties button would be partially visible when it actually should be hidden. This causes a very unusual UI in which buttons overlap.

![problem with hidden control](/media/hubs/globalization/IC115288.gif "problem with hidden control") 

**Figure 5:** Dialog box in which the Edit Properties button and the Accept button overlap.

### Button Text

Avoid placing button text into a string variable. Text on a button should never be dynamically linked onto the button from a string variable, but should be placed on the button itself as a property of the button. Button sizes usually have to be adjusted to fit the length of the translation on the button. Localizers have no way of telling which strings in the string table end up on which button at run time. (See **Figure 6.**)

![truncated text](/media/hubs/globalization/IC26606.gif "truncated text") 

**Figure 6:** The string "add job" ("Auftrag hinzufügen" in German) was stored as a text resource. Since the button cannot change its size at run time, part of the text is truncated.

### Text in Graphics

The last area to consider when dealing with graphics involves embedded text. **Figure 7** displays an icon that a developer wants to use to indicate the function of opening a folder. To make sure that the user understands what to do, the developer has added the word "open" to the graphic.

![text in graphic](/media/hubs/globalization/IC154598.jpg "text in graphic") 

**Figure 7:** Translating this embedded text will cost you valuable time and resources.

Using embedded text such as this is helpful if you are only dealing with the English language. However, when you localize your software for another language, you have to translate this graphic for each language edition. Depending on how the graphic was created, this could take some time. Certain graphics packages-such as Microsoft Paint-often take the text you add and convert it to individual pixels. This means that localizers will need to go back into the graphic, change all the pixels from the text color to the background color, and then add the new translation. Furthermore, they must do this for each language into which you are translating.

Suppose you are translating into 24 languages and it takes 10 minutes to adapt each graphic. That one graphic now costs you 240 minutes or four hours of resources. What seemed to be a simple translation has become a half-day project. If you had to adapt just 10 graphics, you have now unnecessarily added five days of work. In addition, even more time might be involved if the background is more complicated, such as if it has many colors, rather than being monochromatic. Besides the extra time spent localizing the graphic, another issue is that there are now 24 different graphics that you have to keep track of. If you have 10 graphics, you would need to deal with 240 different graphics to make sure that they are in the right place and that they are part of the right build.

The better way to handle this is not to add text to a graphic at all. For the previous example, that would save you \$2000-using a \$25-an-hour estimate for labor-to localize 10 graphics for 24 languages. It would also save you the hassle of keeping track of those 240 different graphics. Even if you think there is a very good reason to have text in a graphic, you should ask yourself if it is absolutely essential. If so, you can still minimize the extra work needed. For instance, some graphics packages have a function that stores the text as a separate layer from the graphic itself. This way, when you need to go back into the graphic, you don't have to change it pixel by pixel. You only have to go into the text layer and change it to the new translation. Although storing the text as a separate layer saves you some time in editing, you still must do this for each language you are localizing into, and for each graphic for which you have text. This practice does not spare you from having to track all additional graphics.


