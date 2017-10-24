---
title: Win32 -- FormatMessage
description: 
ms.assetid: 1092f86e-73fd-4aa6-a7bb-8ee908177416
ms.date: 06/28/2016
---
# Win32—FormatMessage

Win32 supports two resource types for storing strings: string tables and message tables. (For more information on message tables, see the section on [Multilingual User Interface (MUI)](https://msdn.microsoft.com/globalization/mt643131).) String tables make sense for short strings and for strings containing only one replacement parameter; message tables are more convenient for alert and error messages that contain more than one replacement parameter. (Message tables support up to 99 parameters.) The FormatMessage API will substitute variables according to each placemarker's numeric label and not according to the label's position in the string. Localizers can freely change a string's word order and FormatMessage will still return correct results. The file format of the message table is not complicated; you can create message tables with a simple text editor. The following code appears in a message table that contains English and German translations of the same strings. The German translation of IDS\_OTHERIMAGE reverses the positions of the replacement parameters.

```C++
// Sample.mc

     LanguageNames=(German=2:msg00002)

    MessageId=1 SymbolicName=IDS_NOFILE

    Language=English

        Cannot open file %1.

        Language=German

        Die Datei %1 kann nicht geöffnet werden.

    MessageId=2 SymbolicName=IDS_OTHERIMAGE

        Language=English

        %1 is a %2 image.

    Language=German

        %2-Abbild ein %1 ist.
```

The syntax for formatting the first message is as follows:

```C++
  // lpBuf must be large enough to hold the formatted message!

        DWORD langID = MAKELANGID(LANG_GERMAN, SUBLANG_GERMAN);

        HMODULE hModule = LoadLibrary(...);

        TCHAR lpBuf[60];

        LPVOID lppArgs[10];

        DWORD len = FormatMessage(

             FORMAT_MESSAGE_FROM_HMODULE|FORMAT_MESSAGE_ARGUMENT_ARRAY,

             hModule, idMsg, langID, lpBuf, sizeof(lpBuf)/sizeof(TCHAR),

             lppArgs);
```

You can use FormatMessage with string tables as well as with message tables, but it is more efficient to use the function with message tables. FormatMessage can retrieve strings from message tables directly, but it cannot access string tables. To format a string from a string table, you would first have to retrieve it with the LoadString function and then pass it in a buffer to FormatMessage. Not only is this an extra step, it's a convoluted extra step.

FormatMessage is particularly useful for a number of reasons. In conjunction with the API call GetLastError, you can use it to format error messages returned by the system. An example of this technique is given in the following ReportError routine. FormatMessage also allows you to specify the language of the string you want to retrieve from a message table. LoadString can retrieve only resources associated with the language of the current thread's locale.

```C++
void ReportError()
 
    {
        LPTSTR lpMessage;

        DWORD dwErrCode = GetLastError();

        FormatMessage(FORMAT_MESSAGE_ALLOCATE_BUFFER |

             FORMAT_MESSAGE_FROM_SYSTEM,

             NULL, // no source buffer needed

             dwErrCode, // error code for this message

             NULL, // default language ID

             (LPTSTR)&lpMessage, // allocated by fcn

             NULL, // minimum size of buffer

             NULL); // no inserts

        MessageBox(NULL, lpMessage, TEXT("File Error"), 

             MB_ICONSTOP | MB_OK );

    }
```


