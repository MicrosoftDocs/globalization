---
title: Mirroring
description: Complex scripts refer to the languages, where the characters aren't laid out in a simple left-to-right progression.
ms.date: 3/26/2024
author: jowilco
---
# Mirroring

For right-to-left (RTL) languages such as Arabic and Hebrew, the text is right-aligned and has a right to left reading order. However, text in a non-RTL language or script can be mixed with RTL text; therefore, the term *bidirectional* (or *BiDi*) text is commonly used. For more information about bidirectional text, see [Text directionality](text-directionality.md).

For RTL languages, user interface elements should also follow the natural direction of right to left. By default, edit controls in a right-to-left document should inherit right-to-left behavior. For example, control handles and pull-down buttons should be *mirrored* on right-to-left documents. If a scroll bar is required, it appears on the left side of the control. These images compare the RTL behavior of Arabic and the LTR behavior of English using Outlook.

:::image type="content" source="images/LTR.png" alt-text="An image showing Microsoft Outlook in English, demonstrating a left-to-right layout.":::

:::image type="content" source="images/RTL.png" alt-text="An image showing Microsoft Outlook in Arabic, demonstrating a right-to-left layout":::

## Mirroring and UI design

When ensuring support for bidirectional text in applications, you should validate:

- User interface (UI) mirroring. UI flow allows right-to-left content to be presented in its native layout. UI design feels local to BiDi markets.
- Consistency in user experience. The design feels natural in right-to-left orientation. UI elements share a consistent layout direction and appear as the user expects them.
- Touch optimization. Like touch UI in nonmirrored UI, elements are easy to reach, and they natural to touch interaction.
- Mixed text support. Text directionality support enables great mixed text presentation (English text on BiDi builds, and vice versa).

For more information about designing applications to support bidirectional text and mirroring, see [Design your app for bidirectional text](/windows/apps/design/globalizing/design-for-bidi-text) and [Adjust layout and fonts, and support RTL](/windows/apps/design/globalizing/adjust-layout-and-fonts--and-support-rtl).

Implementing BiDi and mirroring support in your user interface will largely depend on the technology selected for your UI layer. For examples, see:

- [FlowDirection Enum](/dotnet/api/microsoft.maui.flowdirection) (.NET MAUI)
- [Form.RightToLeftLayout Property](/dotnet/api/system.windows.forms.form.righttoleftlayout) (System.Windows.Forms)
