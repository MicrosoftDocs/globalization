

# Web Resizing Issues

Many developers are taking advantage of the richness of HTML to create an application's UI. This is great for a development team, but causes huge problems for applications that need to be localized into multiple languages. That is because HTML interfaces are a lot harder to resize and readjust after translating the text.

And it's not just UIs that are hard to resize after translation. Ordinary Web pages that utilize the full power of cascading style sheets (CSS) can be an absolute nightmare! People have found that the cost of translating, resizing, and testing HTML UIs is far greater than that of Win32 dialog boxes.

Nevertheless, with the right coding standards, all HTML UI elements can be constructed so that the localization team will have little or no resizing and repositioning work to do. One approach that Microsoft uses internally to accomplish this is called "HTML AutoLayout (HAL)."

The HAL documentation lists a series of rules and the key reasons behind them. These rules are:

-   Rule 1: Never use absolute positions.
-   Rule 2: Dialog boxes should use the available width and height.
-   Rule 3: Each control should be in a separate cell.
-   Rule 4: Allow wrapping text.
-   Rule 5: Separate check boxes and radio buttons from labels.
-   Rule 6: Leave room for growth and avoid fixed-width items.
-   Rule 7: Define methods for sizing buttons, list boxes, and group boxes.
-   Rule 8: Define when to set height.
-   Rule 9: Do not use left or right align exclusively.
-   Rule 10: Avoid inline CSS with values that localization needs to change.

A key point to remember is that HAL is just one approach for achieving zero international resizing. There are probably countless other methods. This is fine as long as they achieve the same result. Even so, other methods will probably benefit from using some of the HAL rules. Another point to bear in mind is that there are already many HTML dialog boxes that are HAL-compliant for the most part. This is especially true for dialog boxes (or windows) that were designed to be resizable.


