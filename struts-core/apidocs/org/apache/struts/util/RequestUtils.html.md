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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/RequestUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/PropertyMessageResourcesFactory.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ResponseUtils.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/RequestUtils.html"><strong>FRAMES</strong></a>    <a href="RequestUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.util
 Class RequestUtils
----------------------

    java.lang.Object
      org.apache.struts.util.RequestUtils

------------------------------------------------------------------------

    public class RequestUtils

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

General purpose utility methods related to processing a servlet request in the Struts controller framework.

**Version:**  
$Rev: 560654 $ $Date: 2007-07-28 20:54:02 -0500 (Sat, 28 Jul 2007) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static Log`

`log`
           Commons Logging instance.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` RequestUtils()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

`static URL`

` absoluteURL(HttpServletRequest request, String path)`
           Create and return an absolute URL for the specified context-relative path, based on the server and context information in the specified request.

`static String`

` actionIdURL(ForwardConfig forward, HttpServletRequest request, ActionServlet servlet)`
           Returns the true path of the destination action if the specified forward is an action-aliased URL.

`static String`

` actionIdURL(String originalPath, ModuleConfig moduleConfig, ActionServlet servlet)`
           Returns the true path of the destination action if the specified forward is an action-aliased URL.

`static String`

` actionURL(HttpServletRequest request, ActionConfig action, String pattern)`
           Return the context-relative URL that corresponds to the specified [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config"), relative to the module associated with the current modules's [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config").

`static Class`

` applicationClass(String className)`
           Return the `Class` object for the specified fully qualified class name, from this web application's class loader.

`static Class`

` applicationClass(String className, ClassLoader classLoader)`
           Return the `Class` object for the specified fully qualified class name, from this web application's class loader.

`static Object`

` applicationInstance(String className)`
           Return a new instance of the specified fully qualified class name, after loading the class from this web application's class loader.

`static Object`

` applicationInstance(String className, ClassLoader classLoader)`
           Return a new instance of the specified fully qualified class name, after loading the class from this web application's class loader.

`static ActionForm`

` createActionForm(FormBeanConfig config, ActionServlet servlet)`
           Create and return an `ActionForm` instance appropriate to the information in `config`.

`static ActionForm`

` createActionForm(HttpServletRequest request, ActionMapping mapping, ModuleConfig moduleConfig, ActionServlet servlet)`
           Create (if necessary) and return an `ActionForm` instance appropriate for this request.

`static StringBuffer`

` createServerStringBuffer(String scheme, String server, int port)`
           Return `StringBuffer` representing the scheme, server, and port number of the current request.

`static StringBuffer`

` createServerUriStringBuffer(String scheme, String server, int port, String uri)`
           Return `StringBuffer` representing the scheme, server, and port number of the current request.

`static String`

` forwardURL(HttpServletRequest request, ForwardConfig forward)`
           Return the context-relative URL that corresponds to the specified `ForwardConfig`.

`static String`

` forwardURL(HttpServletRequest request, ForwardConfig forward, ModuleConfig moduleConfig)`
           Return the context-relative URL that corresponds to the specified `ForwardConfig`.

`static String`

` getServletMapping(ActionServlet servlet)`
           Retrieves the servlet mapping pattern for the specified [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action").

`static Locale`

` getUserLocale(HttpServletRequest request, String locale)`
           Look up and return current user locale, based on the specified parameters.

`static void`

` populate(Object bean, HttpServletRequest request)`
           Populate the properties of the specified JavaBean from the specified HTTP request, based on matching each parameter name against the corresponding JavaBeans "property setter" methods in the bean's class.

`static void`

` populate(Object bean, String prefix, String suffix, HttpServletRequest request)`
           Populate the properties of the specified JavaBean from the specified HTTP request, based on matching each parameter name (plus an optional prefix and/or suffix) against the corresponding JavaBeans "property setter" methods in the bean's class.

`static String`

` printableURL(URL url)`
           Compute the printable representation of a URL, leaving off the scheme/host/port part if no host is specified.

`static StringBuffer`

` requestToServerStringBuffer(HttpServletRequest request)`
           Return `StringBuffer` representing the scheme, server, and port number of the current request.

`static StringBuffer`

` requestToServerUriStringBuffer(HttpServletRequest request)`
           Return the string representing the scheme, server, and port number of the current request.

`static URL`

` requestURL(HttpServletRequest request)`
           Return the URL representing the current request.

`static URL`

` serverURL(HttpServletRequest request)`
           Return the URL representing the scheme, server, and port number of the current request.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

<span id="constructor_detail"></span>

**Constructor Detail**

### RequestUtils

    public RequestUtils()

<span id="method_detail"></span>

**Method Detail**

### absoluteURL

    public static URL absoluteURL(HttpServletRequest request,
                                  String path)
                           throws MalformedURLException

Create and return an absolute URL for the specified context-relative path, based on the server and context information in the specified request.

**Parameters:**  
`request` - The servlet request we are processing

`path` - The context-relative path (must start with '/')

**Returns:**  
absolute URL based on context-relative path

**Throws:**  
`MalformedURLException` - if we cannot create an absolute URL

------------------------------------------------------------------------

### applicationClass

    public static Class applicationClass(String className)
                                  throws ClassNotFoundException

Return the `Class` object for the specified fully qualified class name, from this web application's class loader.

**Parameters:**  
`className` - Fully qualified class name to be loaded

**Returns:**  
Class object

**Throws:**  
`ClassNotFoundException` - if the class cannot be found

------------------------------------------------------------------------

### applicationClass

    public static Class applicationClass(String className,
                                         ClassLoader classLoader)
                                  throws ClassNotFoundException

Return the `Class` object for the specified fully qualified class name, from this web application's class loader.

**Parameters:**  
`className` - Fully qualified class name to be loaded

`classLoader` - The desired classloader to use

**Returns:**  
Class object

**Throws:**  
`ClassNotFoundException` - if the class cannot be found

------------------------------------------------------------------------

### applicationInstance

    public static Object applicationInstance(String className)
                                      throws ClassNotFoundException,
                                             IllegalAccessException,
                                             InstantiationException

Return a new instance of the specified fully qualified class name, after loading the class from this web application's class loader. The specified class **MUST** have a public zero-arguments constructor.

**Parameters:**  
`className` - Fully qualified class name to use

**Returns:**  
new instance of class

**Throws:**  
`ClassNotFoundException` - if the class cannot be found

`IllegalAccessException` - if the class or its constructor is not accessible

`InstantiationException` - if this class represents an abstract class, an interface, an array class, a primitive type, or void

`InstantiationException` - if this class has no zero-arguments constructor

------------------------------------------------------------------------

### applicationInstance

    public static Object applicationInstance(String className,
                                             ClassLoader classLoader)
                                      throws ClassNotFoundException,
                                             IllegalAccessException,
                                             InstantiationException

Return a new instance of the specified fully qualified class name, after loading the class from this web application's class loader. The specified class **MUST** have a public zero-arguments constructor.

**Parameters:**  
`className` - Fully qualified class name to use

`classLoader` - The desired classloader to use

**Returns:**  
new instance of class

**Throws:**  
`ClassNotFoundException` - if the class cannot be found

`IllegalAccessException` - if the class or its constructor is not accessible

`InstantiationException` - if this class represents an abstract class, an interface, an array class, a primitive type, or void

`InstantiationException` - if this class has no zero-arguments constructor

------------------------------------------------------------------------

### createActionForm

    public static ActionForm createActionForm(HttpServletRequest request,
                                              ActionMapping mapping,
                                              ModuleConfig moduleConfig,
                                              ActionServlet servlet)

Create (if necessary) and return an `ActionForm` instance appropriate for this request. If no `ActionForm` instance is required, return `null`.

**Parameters:**  
`request` - The servlet request we are processing

`mapping` - The action mapping for this request

`moduleConfig` - The configuration for this module

`servlet` - The action servlet

**Returns:**  
ActionForm instance associated with this request

------------------------------------------------------------------------

### createActionForm

    public static ActionForm createActionForm(FormBeanConfig config,
                                              ActionServlet servlet)

Create and return an `ActionForm` instance appropriate to the information in `config`.

Does not perform any checks to see if an existing ActionForm exists which could be reused.

**Parameters:**  
`config` - The configuration for the Form bean which is to be created.

`servlet` - The action servlet

**Returns:**  
ActionForm instance associated with this request

------------------------------------------------------------------------

### getServletMapping

    public static String getServletMapping(ActionServlet servlet)

Retrieves the servlet mapping pattern for the specified [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action").

**Returns:**  
the servlet mapping

**Since:**  
Struts 1.3.6

**See Also:**  
[`Globals.SERVLET_KEY`](../../../../org/apache/struts/Globals.html.md#SERVLET_KEY)

------------------------------------------------------------------------

### getUserLocale

    public static Locale getUserLocale(HttpServletRequest request,
                                       String locale)

Look up and return current user locale, based on the specified parameters.

**Parameters:**  
`request` - The request used to lookup the Locale

`locale` - Name of the session attribute for our user's Locale. If this is `null`, the default locale key is used for the lookup.

**Returns:**  
current user locale

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### populate

    public static void populate(Object bean,
                                HttpServletRequest request)
                         throws ServletException

Populate the properties of the specified JavaBean from the specified HTTP request, based on matching each parameter name against the corresponding JavaBeans "property setter" methods in the bean's class. Suitable conversion is done for argument types as described under `convert()`.

**Parameters:**  
`bean` - The JavaBean whose properties are to be set

`request` - The HTTP request whose parameters are to be used to populate bean properties

**Throws:**  
`ServletException` - if an exception is thrown while setting property values

------------------------------------------------------------------------

### populate

    public static void populate(Object bean,
                                String prefix,
                                String suffix,
                                HttpServletRequest request)
                         throws ServletException

Populate the properties of the specified JavaBean from the specified HTTP request, based on matching each parameter name (plus an optional prefix and/or suffix) against the corresponding JavaBeans "property setter" methods in the bean's class. Suitable conversion is done for argument types as described under `setProperties`.

If you specify a non-null `prefix` and a non-null `suffix`, the parameter name must match **both** conditions for its value(s) to be used in populating bean properties. If the request's content type is "multipart/form-data" and the method is "POST", the `HttpServletRequest` object will be wrapped in a `MultipartRequestWrapper`

**Parameters:**  
`bean` - The JavaBean whose properties are to be set

`prefix` - The prefix (if any) to be prepend to bean property names when looking for matching parameters

`suffix` - The suffix (if any) to be appended to bean property names when looking for matching parameters

`request` - The HTTP request whose parameters are to be used to populate bean properties

**Throws:**  
`ServletException` - if an exception is thrown while setting property values

------------------------------------------------------------------------

### printableURL

    public static String printableURL(URL url)

Compute the printable representation of a URL, leaving off the scheme/host/port part if no host is specified. This will typically be the case for URLs that were originally created from relative or context-relative URIs.

**Parameters:**  
`url` - URL to render in a printable representation

**Returns:**  
printable representation of a URL

------------------------------------------------------------------------

### actionURL

    public static String actionURL(HttpServletRequest request,
                                   ActionConfig action,
                                   String pattern)

Return the context-relative URL that corresponds to the specified [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config"), relative to the module associated with the current modules's [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html "interface in org.apache.struts.config").

**Parameters:**  
`request` - The servlet request we are processing

`action` - ActionConfig to be evaluated

`pattern` - URL pattern used to map the controller servlet

**Returns:**  
context-relative URL relative to the module

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### forwardURL

    public static String forwardURL(HttpServletRequest request,
                                    ForwardConfig forward)

Return the context-relative URL that corresponds to the specified `ForwardConfig`. The URL is calculated based on the properties of the [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") instance as follows:

-   If the `contextRelative` property is set, it is assumed that the `path` property contains a path that is already context-relative:
    -   If the `path` property value starts with a slash, it is returned unmodified.
    -   If the `path` property value does not start with a slash, a slash is prepended.
-   Acquire the `forwardPattern` property from the `ControllerConfig` for the application module used to process this request. If no pattern was configured, default to a pattern of `$M$P`, which is compatible with the hard-coded mapping behavior in Struts 1.0.
-   Process the acquired `forwardPattern`, performing the following substitutions:
    -   **$M** - Replaced by the module prefix for the application module processing this request.
    -   **$P** - Replaced by the `path` property of the specified [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config"), prepended with a slash if it does not start with one.
    -   **$$** - Replaced by a single dollar sign character.
    -   **$x** (where "x" is any charater not listed above) - Silently omit these two characters from the result value. (This has the side effect of causing all other $+letter combinations to be reserved.)

**Parameters:**  
`request` - The servlet request we are processing

`forward` - ForwardConfig to be evaluated

**Returns:**  
context-relative URL

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### forwardURL

    public static String forwardURL(HttpServletRequest request,
                                    ForwardConfig forward,
                                    ModuleConfig moduleConfig)

Return the context-relative URL that corresponds to the specified `ForwardConfig`. The URL is calculated based on the properties of the [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") instance as follows:

-   If the `contextRelative` property is set, it is assumed that the `path` property contains a path that is already context-relative:
    -   If the `path` property value starts with a slash, it is returned unmodified.
    -   If the `path` property value does not start with a slash, a slash is prepended.
-   Acquire the `forwardPattern` property from the `ControllerConfig` for the application module used to process this request. If no pattern was configured, default to a pattern of `$M$P`, which is compatible with the hard-coded mapping behavior in Struts 1.0.
-   Process the acquired `forwardPattern`, performing the following substitutions:
    -   **$M** - Replaced by the module prefix for the application module processing this request.
    -   **$P** - Replaced by the `path` property of the specified [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config"), prepended with a slash if it does not start with one.
    -   **$$** - Replaced by a single dollar sign character.
    -   **$x** (where "x" is any charater not listed above) - Silently omit these two characters from the result value. (This has the side effect of causing all other $+letter combinations to be reserved.)

**Parameters:**  
`request` - The servlet request we are processing

`forward` - ForwardConfig to be evaluated

`moduleConfig` - Base forward on this module config.

**Returns:**  
context-relative URL

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### requestURL

    public static URL requestURL(HttpServletRequest request)
                          throws MalformedURLException

Return the URL representing the current request. This is equivalent to `HttpServletRequest.getRequestURL` in Servlet 2.3.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
URL representing the current request

**Throws:**  
`MalformedURLException` - if a URL cannot be created

------------------------------------------------------------------------

### serverURL

    public static URL serverURL(HttpServletRequest request)
                         throws MalformedURLException

Return the URL representing the scheme, server, and port number of the current request. Server-relative URLs can be created by simply appending the server-relative path (starting with '/') to this.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
URL representing the scheme, server, and port number of the current request

**Throws:**  
`MalformedURLException` - if a URL cannot be created

------------------------------------------------------------------------

### requestToServerUriStringBuffer

    public static StringBuffer requestToServerUriStringBuffer(HttpServletRequest request)

Return the string representing the scheme, server, and port number of the current request. Server-relative URLs can be created by simply appending the server-relative path (starting with '/') to this.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
URL representing the scheme, server, and port number of the current request

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### requestToServerStringBuffer

    public static StringBuffer requestToServerStringBuffer(HttpServletRequest request)

Return `StringBuffer` representing the scheme, server, and port number of the current request. Server-relative URLs can be created by simply appending the server-relative path (starting with '/') to this.

**Parameters:**  
`request` - The servlet request we are processing

**Returns:**  
URL representing the scheme, server, and port number of the current request

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### createServerStringBuffer

    public static StringBuffer createServerStringBuffer(String scheme,
                                                        String server,
                                                        int port)

Return `StringBuffer` representing the scheme, server, and port number of the current request.

**Parameters:**  
`scheme` - The scheme name to use

`server` - The server name to use

`port` - The port value to use

**Returns:**  
StringBuffer in the form scheme: server: port

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### createServerUriStringBuffer

    public static StringBuffer createServerUriStringBuffer(String scheme,
                                                           String server,
                                                           int port,
                                                           String uri)

Return `StringBuffer` representing the scheme, server, and port number of the current request.

**Parameters:**  
`scheme` - The scheme name to use

`server` - The server name to use

`port` - The port value to use

`uri` - The uri value to use

**Returns:**  
StringBuffer in the form scheme: server: port

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### actionIdURL

    public static String actionIdURL(ForwardConfig forward,
                                     HttpServletRequest request,
                                     ActionServlet servlet)

Returns the true path of the destination action if the specified forward is an action-aliased URL. This method version forms the URL based on the current request; selecting the current module if the forward does not explicitly contain a module path.

**Parameters:**  
`forward` - the forward config

`request` - the current request

`servlet` - the servlet handling the current request

**Returns:**  
the context-relative URL of the action if the forward has an action identifier; otherwise `null`.

**Since:**  
Struts 1.3.6

------------------------------------------------------------------------

### actionIdURL

    public static String actionIdURL(String originalPath,
                                     ModuleConfig moduleConfig,
                                     ActionServlet servlet)

Returns the true path of the destination action if the specified forward is an action-aliased URL. This method version forms the URL based on the specified module.

**Parameters:**  
`originalPath` - the action-aliased path

`moduleConfig` - the module config for this request

`servlet` - the servlet handling the current request

**Returns:**  
the context-relative URL of the action if the path has an action identifier; otherwise `null`.

**Since:**  
Struts 1.3.6

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
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/RequestUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/PropertyMessageResourcesFactory.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ResponseUtils.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/RequestUtils.html"><strong>FRAMES</strong></a>    <a href="RequestUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
