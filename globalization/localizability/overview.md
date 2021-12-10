---
title: Localizability overview
description: There are many many complications in most software projects that make it hard to localize
---

# Localizability overview

If you think that after an application designed for a single-market has been tested (and possibly launched) it is then an easy matter to generate localized software by just translating a handful of user interface strings, … think again!

There are many complications in most software projects that can make it hard to localize:

- The product is not world ready and does not support 'extended' characters, locales, etc.

- It is not clear to the localization team what files need to be localized.

- Not all the files are in standard localizable format, custom tools need to be used, or source files need to get translated and product needs to be re-compiled.

- It is not clear what strings should be localized or not.
  The string table contains a mixture of user interface strings, registry keys, function calls, etc.
  It is not clear what strings are used for communication between components, and which are displayed to a user, either of the same language or of mixed languages.

- There are string dependencies, strings that need to get localized in a similar or identical way, strings that need to maintain a certain formatting, or strings that can't exceed a certain string length, etc.

- The user interface text uses cryptic or unclear language, or very technical terminology that is not understood by the translators.
  It is also not always easy to use correct gender, case, etc.

- Items are pulled together during run-time and it is not very clear where items are going to be displayed, what keyboard shortcuts can be used, or how much space has to be reserved in dialog boxes for display.

- Backward-compatibility issues show up, terminology (in)consistency, migration issues, etc.

- Areas we're not expanding on here such as testing, engineering, project management, and content authoring/management/publishing.

On top of that there is always pressure of time, high volumes of changes, and so on.
This makes localization a complicated and error-prone process.
It is so hard to predict what strings can be localized and how they can be localized without introducing functional errors, that translating software strings can be compared with walking in a mine field.

The basic problem is that there has never been a framework providing a way to separate strings used for functionality and strings that are displayed in the user interface.
Because of the lack of this framework, people have not been forced to think about impact on localization, and their software designs have not been fully international-enabled.

A resource table means different things for development as for localization.
A resource table for development is a central storage of strings used in the code.
If the string changes, the string can be changed in one location in the resource table, instead of in many places in the code.
It is also a safer practice to do so, not changing code unnecessarily.
Localization sees a resource table as a set of resources that need to get localized, however these strings are not necessarily user interface strings requiring localization.
Some of the strings are used functionally, represent keys, identifiers, etc., and translating them can have negative functional impact.

In some cases information has been added to the source files meant for localization and localizers, however this information is lost during compilation.
Localization normally uses a no-compile process (localizing the compiled binaries instead of the source files), this information is not visible to the localizer.

The best way to move forward is to integrate "thinking about localization" in the design, development, and test cycle.
We need to setup a framework and guidelines to help development with this task.
Support must be provided where needed.

The proposed framework exists of two pieces, the first part is the clear separation of resources in "functionality related resources" and "user interface-related resources," together with solving some of the current limitations and dependencies in the software.
This we call the "language neutral product" (for more information, see [Isolating Localizable Resources](isolate-localizable-resources.md)).

The second part of the proposed framework is pseudo localization.
Pseudo localization is a simulated localized product.
Every string gets replaced by a semi-random pseudo localized string.
The product can then be tested for its localizability, without paying the sometimes expensive costs for an actual translation.
