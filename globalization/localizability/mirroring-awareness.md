---
title: Mirroring awareness
description: For right to left (RTL) languages, not only does the text alignment and text reading order go from right to left, but also the UI elements layout should follow this natural direction of going from right to left.
---

# Mirroring awareness

For right-to-left (RTL) languages, not only does the text alignment and text reading order go from right to left, but also the user interface layout should follow this natural direction of going from right to left.
Of course, this layout change would only apply to localized RTL languages.

Mirroring gives a perfect RTL look and feel to the user interface.
All language versions and flavors of Windows are already mirroring aware and a mirrored application can be created and executed on all Windows platforms (after Windows 2000).
Figure 1 below displays an Arabic mirrored desktop where every element from the "Start" button to tree-view controls are mirrored.

![Arabic Windows XP desktop](./images/Arabic_Desktop.jpg "Arabic Windows XP desktop")

**Figure 1:** Arabic Windows XP desktop

Notice how the parent elements (the window frame and title) as well as the child elements of the dialog (the tree control, the scroll bar) are both mirrored.

Mirroring is in fact nothing else than a coordinate transformation:

- Origin (0,0) is in the upper right corner of a window
- X scale factor = -1 (i.e. x values increase from right to left

![Coordinate transformation](./images/Coordinate_Trans.jpg "Coordinate transformation")

**Figure 2:** Coordinate transformation

To avoid confusion around coordinates, try to replace the concepts of **left** and **right** with the concepts of **near** and **far**.

To minimize the amount of re-write needed for applications to support mirroring, system components such as "GDI" and "User" have been modified to turn mirroring on and off with almost no additional code changes except for a few considerations regarding owner-drawn controls and bitmaps (see Examples).

There are two different approaches to turn mirroring on and off:

- **Compiled application approach:** This is the approach you use when you have full access to the applications source code.
  For example, by [setting DirectionFlow in WPF](/dotnet/framework/wpf/advanced/bidirectional-features-in-wpf-overview).

- **Non-compiled application approach:** This is the approach you use when you have legacy applications for which you have on access to any of the code.
  This is usually done with some resource localization tool.

## Mirroring bug examples

As mentioned in the overview section, except for a few considerations related to owner-drawn controls there are not many code changes required to be fully mirroring-aware.

Most of the mirroring related bugs are in fact related to owner drawn controls.
Here are a few examples:

### Reversed bitmap

![Reversed bitmap](./images/Reversed_Bitmap.jpg "Reversed bitmap")

This happens when the bitmap is drawn in a mirrored device context (DC).
For compiled applications, you can turn the mirroring of the DC off by calling the SetLayout API.
For non-compiled applications, the workaround would be to flip the Windows logo in the localized resources.
A bitmap flipped twice horizontally would be displayed okay!
For more info, see Solution and Code Samples section.

### Off the screen bitmap

![Off the screen bitmap](./images/Off_the_Screen.jpg "Off the screen bitmap")

The owner-drawn command or bitmap is being drawn outside the desired area because its coordinates are expecting the origin to be in the top-left of the window instead of the top-right.
For compiled applications, use MapWindowPoints to get the coordinates of the destination rectangle.
For non-compiled applications, try to turn the inheritance flag of the dialog box off—this solution would only work if the rectangle in not a child of the parent dialog!

### More information

- [Mirroring in Win32](mirroring-in-win32.md)

- [Mirroring in .NET Framework](mirroring-in-dotnet-framework.md)
