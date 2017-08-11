

# Mirroring in .NET Framework

As was true for Web content, the DIR attribute can be used for mirroring text in Web Forms. The *RightToLeft* property-from the *Control* class-is valuable for providing RTL support for Windows Forms, whereas the *MessageBox* class supports RTL and mirroring for message boxes. In the sections that follow, you will learn how to take advantage of this support.

### Mirrored Web Forms

In Microsoft Visual Studio .NET, you can create ASP.NET applications by using either Microsoft Visual Basic .NET or Microsoft Visual C\# .NET. The guidelines that you should follow are basically the same as those you have just seen for mirroring Web content. When you design Arabic Web Forms pages, the best way to make text flow from right to left is to use the DIR attribute. As with Web content, this attribute is usually placed in the &lt;HTML&gt; tag or the &lt;BODY&gt; tag. Controls and HTML elements on the page then inherit the specified direction.

You can set the DIR attribute at a DOCUMENT object level. All the controls on the form will inherit the same settings. However, the DIR attribute can be used individually with other tags such as &lt;TABLE&gt; and in Web Forms controls, as in the following example, which allows items to be displayed from right to left:

&lt;TABLE dir="rtl" ...&gt;&lt;asp:TextBox dir="rtl" ...&gt;  

### Mirrored Windows Forms

Windows applications created in the .NET Framework allow you to access operating-system services and to take advantage of other benefits that your user's computing environment provides. Also, you can access data using ADO.NET. Additionally, GDI+ allows you to do advanced drawing and painting within your forms. Finally, your Windows applications can make calls to methods exposed through XML Web services.

Windows Forms can be standard windows, multiple-document interface (MDI) windows, dialog boxes, or display surfaces for graphical routines. The easiest way to define the UI for a form is to place controls on its surface. Forms are objects that have several functions. The objects expose properties that define the forms' appearance, methods which define their behavior, and events which define their interaction with the user. Windows Forms are controls because they inherit from the *Control* class. This class has a key property for RTL support-the *RightToLeft* property-which specifies whether the text is displayed from right to left. The form itself supports the *RightToLeft* property, as do all your controls.

**[Table 1: Values for the RightToLeft property]**
| **[Value]** | **[Description]**                  |
|-------------|------------------------------------|
| [Inherit]   | [The direction in which the text is rendered is inherited from the parent control.] |
| [No]        | [The text is rendered from left to right. This is the default value.]               |
| [Yes]       | [The text is rendered from right to left.]                                          |

What about design time? The Windows Forms Designer takes into account the effects of the *RightToLeft* property on controls. For example, when you set the *RightToLeft* property of the form to *Yes*, the property automatically updates the display of the form in the designer, so that the form's caption appears in the title bar right-aligned, as at run time. When the *RightToLeft* property value is set to *RightToLeft.Yes,* the horizontal alignment of the control's elements is reversed, yet the elements' alignment values are unchanged. For example, in a *TextBox* control with the *TextAlign* property value of *HorizontalAlignment.Left*, text is displayed right-aligned, but the property value remains *HorizontalAlignment.Left*. However, if the *RightToLeft* property value is set to *RightToLeft.Yes* and if the *TextAlign* property is set to *HorizontalAlignment.Right*, the text is displayed left-aligned.

Windows Forms don't support mirroring directly, as they do the *RightToLeft* property. Instead, you create your own controls to be displayed as you need. You can develop your own *RTLTreeview* control, for example, which inherits from the *Treeview* control and changes its style to be mirrored.

On some occasions, you might want to create a basic form with settings and properties such as a watermark or a certain control layout that you will then use again within a project. Each new form can contain modifications to the original form template. The solution is to use Windows Forms inheritance, which is a feature offered with the .NET Framework class library. For example, using inheritance you can build your own mirrored form by inheriting from the *System.Windows.Forms.Form* class and changing the window style of *System.-Windows.Forms.Form*.

### Message Boxes

As its name suggests, the *MessageBox* class represents the message box; the *Show* method of this class displays a message box that can contain text, buttons, and symbols that inform and instruct the user. The *MessageBox* class fully supports RTL reading order and mirroring. The *Show* method of the *MessageBox* class takes constants defined in the *MessageBoxOptions* enumeration as parameters. These constants include *RtlReading* and *RightAlign,* both of which enable the message box to display bidirectional text. The following code illustrates how to display an Arabic message box:

```VB
[Visual Basic]
MessageBox.Show([put here your Arabic text],
MessageBoxButtons.OK,
MessageBoxIcon.Question,
MessageBoxDefaultButton.Button1,
MessageBoxOptions.RtlReading Or MessageBoxOptions.RightAlign)
```

*RtlReading* is responsible for ensuring that the text in the message box is displayed with RTL reading order, with mirroring applied. *RightAlign* allows the text to be right-aligned only, but does not enforce RTL reading order or mirroring in the message box.
