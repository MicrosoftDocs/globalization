---
title: Localization Tools
description: Using the proper resource editor tools can make the localization of product resources quick and easy.
ms.assetid: 69222719-1867-459f-be10-14cffa11227a
ms.date: 03/16/2016
---
# Localization Tools

There are several ways to localize software product files. One method is to edit the original resource files before the compilation process takes place. A second method is to localize the final compiled binaries of the product, and then to either save the localized resources into the same binaries or into a separate localization database. Most localization tools are capable of handling either or both of these methods. Regardless of the localization method you choose, using the proper resource editor tools can make the localization of product resources quick and easy. Effective localization tools should also be able to create the localized version of the corresponding original file. This original file can be a resource file or a compiled file, depending on the localization team's choice of tools and localization process.

There are many good localization tools that are commercially available. Before choosing one, be aware of the various criteria that a localization tool should meet. Besides the ability to translate the string resources within the localization tool, a few other tasks the tool should perform are to:

-   Change the names, sizes, and styles of the UI fonts.
-   Resize, move, and hide controls as necessary.
-   Change the encoding of the text.
-   Replace graphics and icons with localized ones.
-   Modify keyboard shortcuts.

A tool's ability to track changes that are made to the original resource from build to build is another very useful feature for localizers, since they can see what is updated between builds. This change can involve a string resource, a font size, or a new icon that has been added to the original product files. On the other hand, it is also useful for a tool to track resources that have been localized, as well as who did the localization, and other pertinent information. These types of statistics and the percentage of localization work completed help the localization manager track and plan the activities of the localization team.

The localization tool should be able to extract and edit a software project's different resource-file formats, which can include INF, Microsoft Win32 resource files, Extensible Markup Language (XML), and many other file formats. The localization team needs to choose the appropriate localization tool in accordance with the resource-file format used in the project.

Another requirement of a good localization tool involves its handling of localization glossaries. (For more information on localization glossaries, see "Localization Outsourcing" in "[Establishing Localization Guidelines](https://msdn.microsoft.com/en-US/library/mt662353)".) The tool that creates these useful glossaries helps the localizers look up the translation of English strings within the glossaries, thus providing a consistent translation. Recycling the localization glossaries allows automated translation of any new string resources in the product that resemble previously translated strings, a practice which will significantly reduce localization costs. Finally, the tool should provide a way to add instructions on how to localize the resources; this will make localization easier and more efficient.

Of course, effective localization results not only from having the proper tools but from having the right people to perform all necessary tasks in the localization process. The following section identifies the team members on a typical localization project and examines each member's roles and responsibilities.


