This documentation is archived and is not being maintained.

# Resource Handling in the .NET Framework

The Microsoft .NET Framework offers a simple approach to the way resource files are created and loaded. Through the support offered by the CLR, you can easily provide an MUI solution in your .NET applications. Moreover, with the .NET Framework you can implement MUI in a way that is practically transparent. The [CultureInfo.CurrentUICulture](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.currentuiculture.aspx) property is a vital part of resource handling.

### CurrentUICulture

The CurrentUICulture property of the [CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx) class (from the [System.Globalization Namespace](https://msdn.microsoft.com/en-us/library/system.globalization.aspx)) is a per-thread setting. You can retrieve CurrentUICulture by querying the [Thread.CurrentUICulture](https://msdn.microsoft.com/en-us/library/system.threading.thread.currentuiculture.aspx) property, and you can change CurrentUICulture by setting Thread.CurrentUICulture.Thread.CurrentUICulture is used by the ResourceManager class to look up culture-specific resources at run time.

The CultureInfo class specifies a unique name for each culture based on the Internet Engineering Task Force (IETF) Language Tag standard. This standard uses the format &lt;languagecode2&gt;-&lt;country/regioncode2&gt;, where &lt;languagecode2&gt; is a lowercase two-letter culture code associated with a language, derived from International Organization for Standardization (ISO) 639-1, and where &lt;country/regioncode2&gt; is an uppercase two-letter subculture code derived from ISO 3166. The invariant culture-which is not associated with any particular language, country, or region-is the root of all cultures. A neutral culture is associated with a language and can be used for resources. (The neutral culture is the equivalent of the primary language ID in the Win32 programming paradigm.) For instance, "fr" is a neutral culture indicating that the language you are dealing with is French, but the neutral culture makes no provision about regional differences in language use (country or region) in which French is being used (France, Belgium, Canada, and so on).

A specific culture is associated with both a language and a region and provides formatting-specific information for that particular location. So, for example, "fr-FR" indicates that you are dealing with the French language as spoken in France.

**Figure 1** summarizes this hierarchy, using German and English as examples. Within the neutral culture of German, for instance, are German in Austria, Switzerland, Germany, Liechtenstein, and Luxembourg. The neutral cultures, German and English, are both part of the invariant culture.

![Hierarchy of invariant, neutral, and specific cultures](https://i-msdn.sec.s-msft.com/dynimg/IC856184.png "Hierarchy of invariant, neutral, and specific cultures")

**Figure 1:** Hierarchy of invariant, neutral, and specific cultures

The CurrentUICulture property is set by the framework when the application starts so that it matches the user's default UI language. Alternatively, you can set CurrentUICulture explicitly in your application's code. The following code example sets the CurrentUICulture property to the neutral culture "de" for German.

``` {style="FONT-FAMILY: Consolas, Courier, monospace; MARGIN-LEFT: 30px" xmlns=""}
Thread.CurrentThread.CurrentUICulture = new CultureInfo("de");
```

You can also set the CurrentUICulture property to a specific culture. The following code example sets the CurrentUICulture property to the specific culture "de-DE" for German in Germany:

``` {style="FONT-FAMILY: Consolas, Courier, monospace; MARGIN-LEFT: 30px" xmlns=""}
Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE"); 
```

As you have seen, the CurrentUICulture property can help you handle resources in a culture-specific manner. The following sections will show how resources are created and loaded.

### The Resource Generation Process in the .NET Framework

As in the Win32 programming model, in the .NET Framework your resources should be separated from the rest of your code. Resource files in .NET are created within .resx files; these files consist of XML-based entries that specify objects and strings within XML tags. One advantage of a .resx file is that when opened with a text editor (such as Notepad or Microsoft Word), it can be written to, parsed, and manipulated.

When viewing a .resx file, you can actually see the binary form of an embedded object (a picture, for example) when this binary information is a part of the resource manifest. Apart from this binary information, a .resx file is completely readable and maintainable. A .resx file contains a standard set of header information, which describes the format of the resource entries and specifies the versioning information for the XML that is used to parse the data. Following the header information, each entry is described as a name/value pair. A name/value pair in the .resx format is wrapped in XML code, which describes string or object values. When a string is added to a .resx file, the name of the string is embedded in a &lt;data&gt; tag, and the value is enclosed in a &lt;value&gt; tag.

The resource generation process is straightforward and includes three steps (although the first and second steps are optional):

1.  A .resx file that contains an XML-based description of the resources is compiled into a .resources file by using the ResGen tool (ResGen.exe is installed with Visual Studio 2015). The resources file that is created contains binary resources. The ResGen tool can also perform the reverse transformation, generating a .resx file from a .resources file.
2.  Another optional step is to create a text file that contains resources such as strings and to transform this text file into a .resx file by using the ResXGen tool provided in the Microsoft .NET Framework SDK. Note that the ResXGen tool is different from the ResGen tool mentioned in step 1. Figure 2 shows the .NET resource generation process used in the .NET Framework.
3.  The .resources file is embedded into an assembly by using either the assembly linker tool or a language compiler, such as the C\# compiler (CSC.exe).

![The .NET resource generation process](https://i-msdn.sec.s-msft.com/dynimg/IC856186.png "The .NET resource generation process") 

**Figure 2:** The .NET resource generation process

### Resource Loading in the .NET Framework

The ResourceManager class provides convenient access to culturally appropriate resources at run time. This class manages multiple resources from a common source that has a particular root name, like the hierarchy shown earlier in **Figure 2**. ResourceManager objects provide fallback resource lookup to region-independent and neutral cultures when specific localized resources are not provided. Resource-loading requests are based on the culture that is associated with the current thread. This culture can be set through the Thread.CurrentThread.CurrentUICulture property.

The ResourceManager class provides two methods, GetString and GetObject, which enable an application to load either a string resource or any object (that can be serialized) from an assembly. Both the GetString and the GetObject methods support two types of overloads:

-   An overload where only the name of the resource is used as a parameter.
-   An overload where, besides the name of the resource, an instance of the *CultureInfo* class must be provided. The *CultureInfo* object represents the culture for which the resource is localized.

If the resource is not localized for the culture that is requested (either explicitly through the second overload or implicitly, by using CurrentUICulture), the lookup will fall back using the culture's Parent property, stopping after looking in the default resources.

When you package your application's resources, you must name them using the resource-naming conventions that the CLR expects. The run time identifies a resource by its culture signature, or name, as discussed in "CurrentUICulture" earlier in this chapter. The .NET Framework uses a hub and spoke model to package and deploy resources. This model requires that you place resources in specific locations, so that they can be easily located and used. If you do not compile and name resources as expected, or if you do not place them in the correct locations, the CLR will not be able to locate them.

If your application includes resources for specific cultures (such as "de-DE"), place each specific culture in its own directory. Do not place specific cultures in subdirectories of their respective neutral culture's directory. (For example, do not put the "de-DE" resources in the "de" folder.) If you do so, the application will not be able to find the localized resource.

The hub and spoke model for packaging and deploying resources uses a fallback process to locate appropriate resources. If an application user requests a ResourceSet that is unavailable, the CLR searches the hierarchy of cultures looking for an appropriate fallback resource that most closely matches the user's request, and raises an exception only as a last resort. At each level of the hierarchy, if an appropriate resource is found, the run time uses it. If the resource is not found, the search continues at the next level.

For instance, if an application is localized in French using the "fr-FR" culture for its resources satellite assembly, and if the application is looking for a string that cannot be found in "fr-FR," it will then fall back to the French culture (if available) and try to find the string in the "fr" satellite assembly. If the string is not available at that level, it will then fall back to the default resources in the main assembly. Finally, if the string resource is not found at that level, an exception will be raised. **Figure 3** illustrates the fallback process.

![The .NET resource fallback mechanism](https://i-msdn.sec.s-msft.com/dynimg/IC856185.png "The .NET resource fallback mechanism")

**Figure 3:** The .NET resource fallback mechanism

[Show:]{} Inherited Protected
