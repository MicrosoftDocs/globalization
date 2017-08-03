

# Prioritizing Components for Globalization Testing

Some components are more likely to have globalization problems than others, so part of globalizing the test means adapting your testing practices accordingly. Assign a globalization priority to all components that are going to be tested. Top priority goes to:

-   Code designed to be used on legacy platforms. Particulary platforms or components that handle text data in non-Unicode encodings. Some of them can be identified as those calling non-Unicode functions of the Microsoft Win32 application programming interface (API). Network components or components with console output are assumed to be in this area. Components using standard C run-time (CRT) libraries to handle text input/output (I/O) belong to this group, too.
-   Components that extensively handle text data.
-   Applications using files for data storage or data exchange.
-   Components that have had many globalization problems in the past.

After determining which components are more likely to have serious globalization errors, choose a viable test platform in accordance with your particular circumstances.


