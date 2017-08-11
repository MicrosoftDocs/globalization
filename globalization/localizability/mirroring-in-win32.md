

# Mirroring in Win32

To minimize the amount of rewriting needed for applications to support mirroring, system components such as the GDI and User modules have been adapted to enable control over the mirroring state of the UI objects. Almost no additional code changes are necessary, with the exception of a few things you will need to consider when working with owner-drawn controls and bitmaps. As you will see, new APIs and extended styles for windows let you turn mirroring on and off at the process level, the window level, the dialog-resources level, or even the device-context level. However, before examining the capabilities of system components and APIs that are available when you enable mirroring in code, this chapter will take a quick look at how and when to enable mirroring in resources.

### Enabling Mirroring in Resources

With changes that the Windows team has made to the system's resource loader, you can mirror your applications by simply editing your resources. This is a good approach to use when you want to mirror old components for which the source is not available or is no longer used; it is also beneficial when you want to conduct primary testing of your applications to see if they support mirroring.

You can mirror applications by adding two left-to-right marks (LRMs)-represented by Unicode code point U+200E-in front of the *FileDescription* value of the version stamping. Figure below shows an English Notepad.exe file that has been mirrored with this approach.

![Mirrored by adding two LRMs](/media/hubs/globalization/IC96246.jpg "Mirrored by adding two LRMs") 

**Figure 1:** A Notepad.exe file that has been mirrored by adding two LRMs

Although easy, enabling mirroring in resources offers little flexibility when it comes to just mirroring a specific window or control. In fact, all windows and controls within those windows that belong to the affected process will be automatically mirrored. For that reason, enabling mirroring in code is more flexible than mirroring in resources, since it allows you the freedom to decide what you want mirrored. Keep in mind that a child process created by the mirrored process does not inherit the mirroring style.

### Enabling Mirroring in Code

Although you can activate mirroring through the localization process (with non- compile mirroring), doing so will often reveal some issues that require a code fix. Also, as stated, you might want full control over when to enable mirroring-such as per process, per window, for dialog resources, or per device context, as shown in the following sections-and over which elements you want mirrored. This is only possible through coding and through new mirroring APIs.

#### Activating Mirroring per Process

By activating the mirroring layout on a per-process basis, all windows that are created after activation will be mirrored; but this activation will not affect the existing windows. This approach is very similar to noncompile mirroring, with the exception that the mirroring style within an application can be turned on and off at run time rather than at a binary level, as in the case of noncompile mirroring.

You set the default direction to RTL for a process by calling [[SetProcessDefaultLayout]](https://msdn.microsoft.com/en-us/library/ms633542.aspx) (LAYOUT\_RTL). You can also turn off default mirroring by calling *SetProcessDefaultLayout(0)*. In addition, you can query the current default layout direction as follows:

```C++
BOOL WINAPI
GetProcessDefaultLayout(DWORD *pdwDefaultLayout);  
```

After returning successfully, *pdwDefaultLayout* contains either LAYOUT\_RTL or 0.

Although you can activate mirroring at the process level, there are times you might wish to activate it at a lower level-such as per window. The following section explains when this method is a good option and shows you what extended styles to use.

#### Activating Mirroring per Window

Once the mirroring style is set at a process level, all newly created windows are automatically mirrored. An alternative approach is to activate mirroring on a per-window basis (if not all windows in your application are meant to be mirrored). With this approach, a window can be mirrored upon its creation by calling *CreateWindowEx,* and set by using the extended style WS\_EX\_LAY- OUTRTL.

By default, all child windows of a parent window inherit the mirroring attribute. However, once again, not all windows are necessarily meant to be mirrored; thus you might want to prevent child windows from being mirrored, for example. To remove the mirroring inheritance for child windows, you need to specify the new extended style WS\_EX\_NOINHERITLAYOUT in your call to *CreateWindowEx*.

A good example of a case where you should prevent the mirroring of child windows would be when you have windows that host or import external controls, such as Microsoft ActiveX, Java applets, Component Object Model (COM) objects, and so on. The problem with controls such as these is that you have little ability to manipulate their behavior, and you cannot readily impose mirroring requirements on them.

The following code shows how to toggle the layout of a window between RTL and LTR:

```C++
LONG lExStyles;

// Retrieve the extended style of the window.
lExStyles = GetWindowLong(hWnd, GWL_EXSTYLE);
// Toggle layout.
lExStyles ^= WS_EX_LAYOUTRTL;
// Set extended styles to new value.
SetWindowLong(hWnd, GWL_EXSTYLE, lExStyles);
// Update client area.
InvalidateRect(hWnd, NULL, TRUE);
```

**Important:** Changing the mirroring style on the fly is not always the most efficient way of implementing mirroring of windows. Many controls might not behave as expected and could be improperly mirrored. Therefore, enabling mirroring of windows as they are initially created remains the better approach.

#### Activating Mirroring for Dialog Resources

It's important to distinguish between a window and a dialog box (which does not receive WM\_CREATE, but rather WM\_INITDIALOG). To activate mirroring for dialog boxes, you need to set the mirroring flags in your resource editor and add the extended styles WS\_EX\_LAYOUTRTL and WS\_EX\_NOINHERITLAYOUT. (The second style is only if you want to prevent the inheritance from taking place.)

The only way to switch between mirrored and nonmirrored dialog resources at run time is to have two sets of dialog resources: one mirrored and one nonmirrored. The Dialog Properties property sheet within the resource editor of Microsoft Visual Studio 6 allows you to set the mirroring style of the dialog resources.

![Setting the mirror style](/media/hubs/globalization/IC43275.jpg "Setting the mirror style") 

**Figure 2:** Setting the mirroring style of the dialog resources within the resource editor of Visual Studio 6

#### Activating Mirroring per Device Context

The mirroring technology described up to now applies to all objects in a standard window. These objects, as well as bitmaps and icons in a mirrored window, are all mirrored by default. Obviously, there are some graphics objects, particularly those that include text, that shouldn't be mirrored. Therefore, Microsoft provides several GDI functions in platforms that support mirroring (which, again, includes all versions of Windows 2000 and Windows XP). These functions are shown in the following code:

```C++
BOOL WINAPI 
 SetLayout(HDC hDc, DWORD dwLayout);
DWORD WINAPI 
 GetLayout(HDC hDc);
```

The device context of a mirrored window is mirrored by default. Nevertheless, you can disable mirroring in a device context by calling *SetLayout (hdc, 0)* , and activate it by calling *SetLayout(hdc, LAYOUT\_RTL)*. You might need control over the mirroring properties of a device context in cases when some drawing operation performed by a legacy code is broken by mirroring.

Drawing images that may be sensitive to directionality of the output presents a separate problem. To prevent mirroring of bitmaps, call *SetLayout* with the LAYOUT\_BITMAPORIENTATIONPRESERVED bit set in *dwLayout* :

```C++
SetLayout(hdc, LAYOUT_RTL | LAYOUT_BITMAPORIENTATIONPRESERVED);  
```

Upon successful completion of *GetLayout*, *GetLayout* returns the following:

-   0 if the device context is not mirrored

-   LAYOUT\_RTL if the device context is mirrored

-   LAYOUT\_RTL and LAYOUT\_BITMAP if the device context is mirrored and if the programmer does not want the device context to have mirrored bitmaps

Yet another way to prevent a bitmap from being mirrored is to define NOMIR-RORBITMAP in calls to *BitBlt* and *StretchBlt.*

#### Mirroring and Property Sheets

A tricky situation when enabling mirroring is when you are dealing with property sheets (and wizards). Imagine the case where a property-sheet container has several pages, and only a few of them are localized into an RTL language. Individual pages are made out of dialog templates that can be mirrored separately in the resources. But what about the container? Should the container be mirrored? To avoid confusion and inconsistent behavior with property sheets, the following approaches are among many steps that the system takes in order to decide whether to create a mirrored container:

-   If the first page does not contain the mirroring window style and the client process is not mirrored, the client will not be considered a mirrored client. This can happen when the application loads the first page from a different binary.

-   If the primary resource language of the first page is not Arabic or Hebrew, the client will not be considered a mirrored client. This can happen when the application loads the first page from a different binary (a binary which might not be localized for the same language).

#### Mapping Coordinates

Perhaps one of the biggest issues when it comes to dealing with mirroring is mapping between screen coordinates and client coordinates, or failing to do so. For example, developers often use code such as the following to position a control in a window:

```C++
GetWindowRect(hControl, (LPRECT) &rControlRect);
// Gets coordinates of window in screen coordinates.
ScreenToClient(hDialog, (LPPOINT) &rControlRect.left);
// Maps screen coordinates to client coordinates in dialog box.
ScreenToClient(hDialog, (LPPOINT) &rControlRect.right);
```

In this code, the left edge of a rectangle becomes the right edge in a mirrored window, and vice versa, causing unintended results. The solution is to replace the *ScreenToClient* calls as shown in the following code:

```C++
GetWindowRect(hControl, (LPRECT) &rControlRect);
// Gets coordinates of window in screen coordinates.
MapWindowPoints (NULL, hDialog, (LPPOINT) &rControlRect, 2);
```

This code works because the *MapWindowPoints* API has been modified on platforms that support mirroring. As a result of this modification, *Map-WindowPoints* is able to swap the left- and right-point coordinates of the client window that is being mirrored, whenever two points at a time are passed to this API.

Another common practice that can cause problems in mirrored windows is using offsets in screen coordinates to position objects in a client window, instead of using client coordinates. For example, to position a control in a dialog box, the following code uses the difference in the left edges of the control and the dialog box-in screen coordinates-as the *x* position in client coordinates:

```C++
RECT rcDialog;
RECT rcControl;
HWND hControl = GetDlgItem(hDlg, IDD_CONTROL);
GetWindowRect(hDlg, &rcDialog);
// Gets rect in screen coordinates
GetWindowRect(hControl, &rcControl);
// Takes x position in client coordinates
MoveWindow(hControl, rcControl.left - rcDialog.left, _
 rcControl.top - rcDialog.top, nWidth, nHeight, FALSE);
```

This works fine when the dialog window has an LTR layout, and when the mapping mode of the client is MM\_TEXT. The new *x* position in client coordinates corresponds to the difference in the left edges of the control and the dialog box in screen coordinates. In a mirrored dialog box, however, the roles of left and right are reversed. You can remove the assumption from the previous code that near is left and far is right by using [[MapWindowPoints]](https://msdn.microsoft.com/en-us/library/dd145046.aspx) to go into client coordinates, as shown in the following code sample:

```C++
RECT rcDialog;
RECT rcControl;
HWND hControl = GetDlgItem(hDlg, IDD_CONTROL);
GetWindowRect(hControl, &rcControl);
// MapWindowPoints will work correctly in mirrored
// windows and in non-mirrored windows.
MapWindowPoints(NULL, hDlg, (LPPOINT)&rcControl, 2);
//Now rcControl is in client coordinates.
MoveWindow(hControl, rcControl.left, rcControl.top, nWidth, nHeight, FALSE);
```

There is a common theme in these examples. Instead of thinking in terms of the concrete notions of left and right, you should substitute the more abstract concepts of near and far. The following are some specific guidelines on developing applications that can be mirrored by using the automatic mirroring interfaces:

-   Use client coordinates rather than screen coordinates wherever possible.

-   If necessary, map from screen coordinates to client coordinates.

-   To map points, use *MapWindowPoints* instead of *ClientToScreen* and *ScreenToClient*.

#### Handling Direction-Sensitive Graphics

Direction-sensitive graphics (such as bitmaps and icons) present another challenge with regard to mirroring. Some direction-sensitive graphics can have a different meaning when mirrored. For example, within an LTR layout in a browser, an arrow that points to the left represents the concept of going back to the previous page; an arrow that points to the right would signify going forward to the next page. When these arrows are mirrored for an RTL layout, the meaning will be just the opposite.

![Direction-sensitive arrow](/media/hubs/globalization/IC156676.jpg "Direction-sensitive arrow") 

**Figure 7:** Example of a direction-sensitive arrow that changes meaning when mirrored

------------------------------------------------------------------------

Other graphics should not be mirrored at all, such as legal trademarks or logos because they will make no sense when laid out from right to left.

![direction-sensitive graphic](/media/hubs/globalization/IC60268.jpg "direction-sensitive graphic") 

**Figure 8:** Example of a direction-sensitive graphic that should not be mirrored

------------------------------------------------------------------------

There are several solutions available for dealing with cases such as these. Deciding which of the following four approaches to use depends on the particular situation at hand.

One solution is to temporarily turn off RTL layout of the device context when rendering direction-sensitive bitmaps or icons; you can then turn it back on once mirroring is completed. The problem with this approach is that sometimes you don't have access to the device context where the graphics will be rendered. (An example of this is when passing your icon or bitmap handle to a third-party DLL that will display the image for you.)

Another solution is to have two different sets of graphics in your resources-one set to be used when the drawing destination is LTR-oriented, and the other set to be used when the drawing destination is RTL-oriented. The first set will contain the original, LTR graphics. The second set will contain a copy of the first set of graphics with modifications made only to those graphics needing to reflect the RTL orientation. You can then choose which set to load and render based on whether the set will be rendered in a mirrored or nonmirrored situation. In other words, for nonmirrored device contexts you would load the original set of nonmirrored graphics, and for mirrored device contexts you would load the set that contained the assortment of mirrored and nonmirrored graphics. (In the latter case, when mirrored graphics are rendered on a mirrored device context, they will be mirrored again and thus revert back to the way you want them to be displayed.) Depending on the number of direction-sensitive graphics that you have in your project, this approach might not be your best choice if you have a lot of graphics that should not be mirrored, since duplicating those will increase the size of your resources.

As a third solution, if you ship a separate set of binaries based on the target localized languages, you can let your localization team mirror those graphics elements using a resource editor. (Most resource editors let you flip images in both *x* and *y* directions nowadays.) A final solution-especially when you don't have direct access to the device context where the graphics will be rendered-is to create a mirrored copy of the resource. You then pass this mirrored copy instead of the original, nonmirrored one. (Again, when the mirrored graphics are rendered on a mirrored device context, they will revert back to their original, intended look.) The following sample code illustrates how to mirror both a bitmap and an icon when each's handle is passed:

```C++
HBITMAP CreateMirroredBitmap( HBITMAP hbmOrig)
    {
                   HDC hdc, hdcMem1, hdcMem2;
     HBITMAP hbm = NULL, hOld_bm1, hOld_bm2;
     BITMAP bm;
     if (!hbmOrig)
     return NULL;
     if (!GetObject(hbmOrig, sizeof(BITMAP), &bm))
     return NULL;

     // Grab the screen DC.
     hdc = GetDC(NULL);
     if (hdc)
     {
     hdcMem1 = CreateCompatibleDC(hdc);
     if (!hdcMem1)
     {
     ReleaseDC(NULL, hdc);
     return NULL;
     }
     hdcMem2 = CreateCompatibleDC(hdc);
     if (!hdcMem2)
     {
     DeleteDC(hdcMem1);
     ReleaseDC(NULL, hdc);
     return NULL;
     }
     hbm = CreateCompatibleBitmap(hdc, bm.bmWidth, bm.bmHeight);
     if (!hbm)
     {
     ReleaseDC(NULL, hdc);
     DeleteDC(hdcMem1);
     DeleteDC(hdcMem2);
     return NULL;
     }
     // Flip the bitmap.
     hOld_bm1 = (HBITMAP)SelectObject(hdcMem1, hbmOrig);
     hOld_bm2 = (HBITMAP)SelectObject(hdcMem2 , hbm );
     SetLayout(hdcMem2, LAYOUT_RTL);
     BitBlt(hdcMem2, 0, 0, bm.bmWidth, bm.bmHeight, hdcMem1, 0, 0, SRCCOPY);
     SelectObject(hdcMem1, hOld_bm1 );
     SelectObject(hdcMem1, hOld_bm2 );
     DeleteDC(hdcMem1);
     DeleteDC(hdcMem2);
     ReleaseDC(NULL, hdc);
     }
     return hbm;
                   }

    HICON CreateMirroredIcon(HICON hiconOrg)
    {
                   HDC hdcScreen, hdcBitmap, hdcMask = NULL;
     HBITMAP hbm, hbmMask, hbmOld,hbmOldMask;
     BITMAP bm;
     ICONINFO ii;
     HICON hicon = NULL;
     hdcBitmap = CreateCompatibleDC(NULL);
     if (hdcBitmap)
     {
     hdcMask = CreateCompatibleDC(NULL);
     if( hdcMask )
     {
     SetLayout(hdcBitmap, LAYOUT_RTL);
     SetLayout(hdcMask, LAYOUT_RTL);
     }
     else
     {
     DeleteDC( hdcBitmap );
     hdcBitmap = NULL;
     }
     }
     hdcScreen = GetDC(NULL);
     if (hdcScreen)
     {
     if (hdcBitmap && hdcMask)
     {
     if (hiconOrg)
     {
     if (GetIconInfo(hiconOrg, &ii) && GetObject(ii.hbmColor, _
     sizeof(BITMAP), &bm)
     {
     // Do the cleanup for the bitmaps.
     DeleteObject( ii.hbmMask );
     DeleteObject( ii.hbmColor );
     ii.hbmMask = ii.hbmColor = NULL;
     hbm = CreateCompatibleBitmap(hdcScreen,
     bm.bmWidth, bm.bmHeight);
     hbmMask = CreateBitmap(bm.bmWidth, bm.bmHeight,1, 1, NULL);
     hbmOld = (HBITMAP)SelectObject(hdcBitmap, hbm);
     hbmOldMask = (HBITMAP)SelectObject(hdcMask,hbmMask);
     DrawIconEx(hdcBitmap, 0, 0, hiconOrg,bm.bmWidth, _
     bm.bmHeight, 0, NULL, DI_IMAGE);
     DrawIconEx(hdcMask, 0, 0, hiconOrg, _
     bm.bmWidth,bm.bmHeight, 0, NULL, DI_MASK);
     SelectObject(hdcBitmap, hbmOld);
     SelectObject(hdcMask, hbmOldMask);

     // Create the new mirrored icon and delete bitmaps

     ii.hbmMask = hbmMask;
     ii.hbmColor = hbm;
     hicon = CreateIconIndirect(&ii);
     DeleteObject(hbm);
     DeleteObject(hbmMask);
     }
     }
     }
     ReleaseDC(NULL, hdcScreen);
     }

     if (hdcBitmap)
     DeleteDC(hdcBitmap);
     if (hdcMask)
     DeleteDC(hdcMask);
     return hicon;
}
```

#### Mirroring and Image-List Controls

A good way of dealing with graphics is to use image-list controls because of the wide flexibility these controls offer. Image-list controls are also used to manage graphics for other controls like tree-view and list-view controls. However, there is one potential issue that can arise. In the case of direction-sensitive bitmaps, if you are using an image list whose contents will be rendered on a mirrored device context, the image list will not have direct access to the image-list device context. On Windows XP, you can use the image-list flags ILC\_MIRROR and ILC\_PERITEMMIRROR to enable mirroring. If your code needs to run on Windows 2000, Windows 98, or Windows Me with mirroring support, you can use the previous code samples to mirror the direction-sensitive bitmap or icon before adding it to the list. Note, however, that the previous code will allow you to mirror such bitmaps and icons if you are adding these images to the list one by one. If you are adding images to the list more than one at a time, you can tweak the previous code to mirror each element inside the image strip that you are adding to the list. For example, you can modify *CreateMirroredBitmap(),* so that instead of this line:

```C++
BitBlt(hdcMem2, 0, 0, bm.bmWidth, bm.bmHeight, hdcMem1, 0, 0, SRCCOPY); 
```

you can have the following code, where *Width* is the width of each individual image in the image strip that will be added to the image list:

```C++
int n = bm.bmWidth / Width, i;
for(i =0; i< n; i++)
 {
 BitBlt(hdcMem2, i * Width + 0, 0, Width, bm.bmHeight, hdcMem1, _
 (n - i - 1) * Width, 0, SRCCOPY);
 } 
```

Specifying the width of each individual image will achieve the same effect on Windows 2000, Windows 98, or Windows Me as if you were to specify ILC\_PERITEMMIRROR on Windows XP.


