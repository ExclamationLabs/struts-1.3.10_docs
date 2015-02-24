------------------------------------------------------------------------

<span id="navbar_top"></span> [](#skip-navbar_top "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_top_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/upload/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../org/apache/struts/validator/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Package org.apache.struts.util
------------------------------

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications.

**See:**
           [**Description**](#package_description)

**Class Summary**

**[ImageButtonBean](../../../../org/apache/struts/util/ImageButtonBean.html.md "class in org.apache.struts.util")**

A simple JavaBean to encapsulate the request parameters sent for an HTML input element of type image.

**[IteratorAdapter](../../../../org/apache/struts/util/IteratorAdapter.html.md "class in org.apache.struts.util")**

Utility method for converting Enumeration to an Iterator class.

**[LabelValueBean](../../../../org/apache/struts/util/LabelValueBean.html.md "class in org.apache.struts.util")**

A simple JavaBean to represent label-value pairs.

**[MessageResources](../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util")**

General purpose abstract class that describes an API for retrieving Locale-sensitive messages from underlying resource locations of an unspecified design, and optionally utilizing the `MessageFormat` class to produce internationalized messages with parametric replacement.

**[MessageResourcesFactory](../../../../org/apache/struts/util/MessageResourcesFactory.html.md "class in org.apache.struts.util")**

Factory for `MessageResources` instances.

**[ModuleUtils](../../../../org/apache/struts/util/ModuleUtils.html.md "class in org.apache.struts.util")**

General purpose utility methods related to module processing.

**[PropertyMessageResources](../../../../org/apache/struts/util/PropertyMessageResources.html.md "class in org.apache.struts.util")**

Concrete subclass of `MessageResources` that reads message keys and corresponding strings from named property resources in a ***similar*** manner (see *modes* below) that `java.util.PropertyResourceBundle` does.

**[PropertyMessageResourcesFactory](../../../../org/apache/struts/util/PropertyMessageResourcesFactory.html.md "class in org.apache.struts.util")**

Factory for `PropertyMessageResources` instances.

**[RequestUtils](../../../../org/apache/struts/util/RequestUtils.html.md "class in org.apache.struts.util")**

General purpose utility methods related to processing a servlet request in the Struts controller framework.

**[ResponseUtils](../../../../org/apache/struts/util/ResponseUtils.html.md "class in org.apache.struts.util")**

General purpose utility methods related to generating a servlet response in the Struts controller framework.

**[ServletContextWriter](../../../../org/apache/struts/util/ServletContextWriter.html.md "class in org.apache.struts.util")**

A PrintWriter implementation that uses the logging facilities of a `javax.servlet.ServletContext` to output its results.

**[TokenProcessor](../../../../org/apache/struts/util/TokenProcessor.html.md "class in org.apache.struts.util")**

TokenProcessor is responsible for handling all token related functionality.

**[WildcardHelper](../../../../org/apache/struts/util/WildcardHelper.html.md "class in org.apache.struts.util")**

This class is an utility class that perform wilcard-patterns matching and isolation taken from Apache Cocoon.

 

**Exception Summary**

**[ModuleException](../../../../org/apache/struts/util/ModuleException.html.md "class in org.apache.struts.util")**

Used for specialized exception handling.

 

<span id="package_description"></span>

Package org.apache.struts.util Description
------------------------------------------

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications.
 <span id="doc.Description"></span>

[[Introduction]](#doc.Intro) [[Beans]](#doc.Beans) [[Servlet Utilities]](#doc.Utilities) [[Message Resources]](#doc.Messages)

------------------------------------------------------------------------

<span id="doc.Intro"></span>

### Introduction

The Struts Utilities Package offers several families of classes that assist in solving commonly encountered problems when building web applications. Most of the classes in this package do not rely on the controller servlet framework, or the custom tag libraries, so they are also suitable for general Java application programming. The following families are included:

-   [Beans](#doc.Beans) - A small set of utility beans useful for encapsulating form elements.
-   [Servlet Utilities](#doc.Utilities) - A set of classes useful for working with servlet-related classes.
-   [Message Resources](#doc.Messages) - A family of classes that features access to internationalized message strings based on a message key coupled with a `java.util.Locale` object representing a particular user's preferred language.

------------------------------------------------------------------------

<span id="doc.Beans"></span>

### Beans

The `ImageButtonBean` is a simple JavaBean to encapsulate the request parameters sent for an HTML input element of type image. The `LabelValueBean` is a simple JavaBean to represent label-value pairs, especially useful for.html.md option elements.

------------------------------------------------------------------------

<span id="doc.Utilities"></span>

### Servlet Utilities

The `RequestUtils` is a general purpose utility methods related to processing a servlet request. The `ResponseUtils` is a general purpose utility methods related to generating a servlet response. The `ServletContextWriter` is a PrintWriter implementation that uses the logging facilities of a `javax.servlet.ServletContext` to output its results.

------------------------------------------------------------------------

<span id="doc.Messages"></span>

### Message Resources

##### Background

Modern applications often include the requirement to support multiple languages, for users who prefer to interact in a language other than the default language configured on the server platform. In addition, sentences often need to be constructed, with dynamic content whose placement in the message depends on the standard sentence structure in that particular language.

The standard Java platform includes a family of classes (`java.util.ResourceBundle`) designed to support looking up message strings based on a standard "key". The resource bundle classes automatically access a Java class (or properties file) that is named with a naming convention that includes the Locale to which messages in that class (or file) pertain. However, this selection is based only on the default Locale of the server platform, and cannot be adjusted on a per-user basis as required for an internationalized web application.

Struts includes a family of classes (`org.apache.struts.util.MessageResources`) that extends the basic approach to looking up message strings by key, allowing you to optionally specify a Locale along with the key. In this way, you can build applications that let your users select which Locale they wish to operate within, and then look up messages in that language - using the same message keys no matter what language is selected.

In addition to supporting dynamic selection of a Locale for message lookup, the `MessageResources` family of classes optionally allow you to specify up to four parameter replacement objects, which are used to replace the parameter placeholders "{0}" through "{3}" in the retrieved message. This replacement uses the facilities of the standard Java `java.text.MessageFormat` class, which supports many extended formatting capabilities as well.

For more information about internationalized messages, consult the following resources in your Java Development Kit documentation bundle:

-   *Internationalization Info* - General information on Java's standard support for internationalized applications can be found at `<$JAVA_HOME/docs/guide/internat/index.html.md>`. The "Internationalization Overview" section includes useful information about Locales, localized resources, message formatting, and other relevant topics.
-   *Internationalization Tutorial* - The Java Language Tutorial has a comprehensive trail covering internationalization, available at: <http://java.sun.com/docs/books/tutorial/i18n/index.html.md>.
-   *Javadoc APIs* - You will want to consult the Javadoc API documentation for the following standard Java classes:
    -   `java.text.MessageFormat`
    -   `java.util.ResourceBundle`
    -   `java.util.PropertyResourceBundle`
    -   `java.util.Properties` - See the documentation for the `load()` method for the valid syntax of properties files that you prepare.

##### Using the Standard MessageResources Implementation

The standard `MessageResources` implementation provided by the Struts library uses Java properties files to initialize message strings, in a manner very similar to that supported by the `java.util.PropertyResourceBundle` class. The following steps are required to use these facilities in your Java application.

First, prepare a Java properties file for each language (or Locale) in which you wish to support your messages. The filenames you use must conform to the naming convention for property resource bundles, as described in the documentation referenced above. Be sure you use the same message keys in each file to identify the same message.

For example, you might prepare files in French, Spanish, and English that contain language-specific versions of the word "Hello". The French file would be named `Messages_fr.properties` and contain the following:

        hi=Bonjour

while the Spanish and English files would be named `Messages_es.properties` and `Messages_en.properties` respectively. The corresponding message string definitions would say `hi=Hola` and `hi=Hello` in these files.

Second, place these properties files into the class path for your application, exactly as you would with class files themselves. The name actually used to load resources will look like a fully qualified Java class name (with appropriate package prefixes), so the file should be nested inside a directory structure that matches the packaging (either in an unpacked directory, or within a JAR file, as appropriate). For example, assume you place directory "foo" on your classpath, and stored the above properties files in directory "foo/com/mycompany/mypackage". (If you were using a JAR file like "foo.jar" instead, the files would be in directory "com/mycompany/mypackage" within the JAR file).

Third, initialize a `MessageResources` object that corresponds to the set of properties files for a particular name, within a particular package. The easiest way to do this is to initialize a variable in your main application class, like this:

        public static MessageResources messages =
        MessageResources.getMessageResources("com.mycompany.mypackage.Messages");

Note that the "com.mycompany.mypackage" part of the name matches the package directory into which you placed your properties files, and "Messages" is the filename prefix for the particular family of properties files supported by this `MessageResources` instance. Depending on your development process, you might find it convenient to store all message strings for an entire application in a single properties file family, or to have several families - in Struts, for example, there is a family of properties files for each Java package.

To access a message string with a particular Locale, execute a statement like this:

        Locale locale = ... select the locale to be used ...
        String message = messages.getMessage(locale, "hi");

In this case, the variable `message` will contain the message string corresponding to the key "hi", in the language that corresponds to the locale that was selected.

For an example of message formatting with replaceable parameters, assume that the message strings looked like this, instead (only the English version is shown - corresponding changes would be made in the other files):

        hi=Hello {0}

Now, you can personalize the retrieved message like this:

        Locale locale = ... select the locale to be used ...
        String name = "Joe";
        String message = messages.getMessage(locale, "hi", name);

and the marker "{0}" will have been replaced by the specified name (Joe), no matter which language is in use. See the JavaDoc API documentation for the `java.text.MessageFormat` class for more advanced uses of the parameter replacement mechanism.

##### Developing Your Own MessageResources Implementation

In the above example, we were using the default `MessageResources` implementation supplied by Struts, which uses property files to store the message strings. It is also possible to create customized mechanisms to retrieve messages (such as loading them on demand from a database). The steps required are as follows:

-   Create a customized subclass of `org.apache.struts.util.MessageResources` that implements message lookup operations as you require.
-   Create a customized subclass of `org.apache.struts.util.MessageResourcesFactory` that will create an instance of your custom `MessageResources` class when the `createResources` method is called. Note that the "config" argument to this method can be used to select families of messages in any manner appropriate to your needs - you are not required to emulate the "fully qualified Java class name" approach that is used by the standard `PropertyMessageResourcesFactory` class.
-   Tell the `MessageResourcesFactory` class the name of the customized `MessageResourcesFactory` implementation to use when creating new factory instances.
-   Create a new factory instance.
-   Ask the new factory instance to create a `MessageResources` instance for you.

A code example that illustrates this technique is:

        MessageResourcesFactory.setFactoryClass("com.mycompany.mypkg.MyFactory");
        MessageResourcesFactory factory = MessageResourcesFactory.createFactory();
        MessageResources resources =
        factory.createResources("configuration information");

Once you have created your custom MessageResources instance, you utilize it to access message strings (with or without parameter replacement objects), exactly as we illustrated with the standard implementation in the previous section.

##### Using MessageResources With Struts

If your application uses the Struts controller servlet, you can optionally configure Struts to load an application-specific message resources instance for you, and make it available as a servlet context attribute (in JSP terms, an application-scope bean). This mechanism is managed by setting the following servlet initialization parameters in the web application deployment descriptor:

-   **application** - The configuration string that will be passed to the `createResources()` method of the message resources factory, in order to identify the family of resources to be supported. If you use the standard message resources factory, this must be the base fully qualified name of the property resources files used to contain these messages, as illustrated above.
-   **factory** - Fully qualified Java class name of the `MessageResourcesFactory` to be used. By default, the standard implementation provided by Struts (`org.apache.struts.util.PropertyMessageResourcesFactory`) will be used.

Struts provides several JSP custom tags that assume the existence of a `java.util.Locale` attribute in the user's session, under the key named by the constant string value of `Action.LOCALE_KEY`. Your own application logic can set this attribute at any time, or you can ask Struts to set it automatically (if not already set) based on the `Accept-Language` HTTP header included with the request. There are two mechanisms by which you request Struts to perform this service:

-   To have this service performed on every request submitted to the controller servlet, set the servlet initialization parameter `locale` to the value `true` in the application deployment descriptor.
-   To have this service performed by a JSP page when it is accessed directly by a user, utilize a `<form.html.md ... locale="true" ... />` tag at the top of each page.

------------------------------------------------------------------------

<span id="navbar_bottom"></span> [](#skip-navbar_bottom "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_bottom_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"> <strong>Package</strong> </td>
<td align="left">Class </td>
<td align="left"><a href="package-use.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/upload/package-summary.html.md"><strong>PREV PACKAGE</strong></a>   <a href="../../../../org/apache/struts/validator/package-summary.html"><strong>NEXT PACKAGE</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/package-summary.html"><strong>FRAMES</strong></a>    <a href="package-summary.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
