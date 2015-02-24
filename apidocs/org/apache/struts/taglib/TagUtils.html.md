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
<td align="left"><a href="class-use/TagUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/taglib/TagUtils.html"><strong>FRAMES</strong></a>    <a href="TagUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.taglib
 Class TagUtils
------------------------

    java.lang.Object
      org.apache.struts.taglib.TagUtils

------------------------------------------------------------------------

    public class TagUtils

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Provides helper methods for JSP tags.

**Since:**  
Struts 1.2

**Version:**  
$Rev: 471754 $

------------------------------------------------------------------------

<span id="constructor_summary"></span>

**Constructor Summary**

`protected`

`TagUtils()`
           Constructor for TagUtils.

  <span id="method_summary"></span>

**Method Summary**

` Map`

` computeParameters(PageContext pageContext, String paramId, String paramName, String paramProperty, String paramScope, String name, String property, String scope, boolean transaction)`
           Compute a set of query parameters that will be dynamically added to a generated URL.

` String`

` computeURL(PageContext pageContext, String forward, String href, String page, String action, String module, Map params, String anchor, boolean redirect)`
            

` String`

` computeURL(PageContext pageContext, String forward, String href, String page, String action, String module, Map params, String anchor, boolean redirect, boolean encodeSeparator)`
            

` String`

` computeURLWithCharEncoding(PageContext pageContext, String forward, String href, String page, String action, String module, Map params, String anchor, boolean redirect, boolean useLocalEncoding)`
           Compute a hyperlink URL based on the `forward`, `href`, `action` or `page` parameter that is not null.

` String`

` computeURLWithCharEncoding(PageContext pageContext, String forward, String href, String page, String action, String module, Map params, String anchor, boolean redirect, boolean encodeSeparator, boolean useLocalEncoding)`
           Compute a hyperlink URL based on the `forward`, `href`, `action` or `page` parameter that is not null.

` String`

` encodeURL(String url)`
           URLencodes a string assuming the character encoding is UTF-8.

` String`

` encodeURL(String url, String enc)`
           Use the new URLEncoder.encode() method from Java 1.4 if available, else use the old deprecated version.

` String`

` filter(String value)`
           Filter the specified string for characters that are senstive to HTML interpreters, returning the string with these characters replaced by the corresponding character entities.

` String`

` getActionMappingName(String action)`
           Return the form action converted into an action mapping path.

` String`

` getActionMappingURL(String action, PageContext pageContext)`
           Return the form action converted into a server-relative URL.

` String`

` getActionMappingURL(String action, String module, PageContext pageContext, boolean contextRelative)`
           Return the form action converted into a server-relative URL.

` ActionMessages`

` getActionMessages(PageContext pageContext, String paramName)`
           Retrieves the value from request scope and if it isn't already an `ActionMessages`, some classes are converted to one.

`static TagUtils`

`getInstance()`
           Returns the Singleton instance of TagUtils.

` ModuleConfig`

` getModuleConfig(PageContext pageContext)`
           Return the default ModuleConfig object if it exists, null if otherwise.

` ModuleConfig`

` getModuleConfig(String module, PageContext pageContext)`
           Return the specified ModuleConfig object for the given prefix if it exists, otherwise a NullPointerException will be thrown.

` int`

` getScope(String scopeName)`
           Converts the scope name into its corresponding PageContext constant value.

` Locale`

` getUserLocale(PageContext pageContext, String locale)`
           Look up and return current user locale, based on the specified parameters.

` boolean`

` is.html.md(PageContext pageContext)`
           Returns true if the custom tags are in XHTML mode.

` Object`

` lookup(PageContext pageContext, String name, String scopeName)`
           Locate and return the specified bean, from an optionally specified scope, in the specified page context.

` Object`

` lookup(PageContext pageContext, String name, String property, String scope)`
           Locate and return the specified property of the specified bean, from an optionally specified scope, in the specified page context.

` String`

` message(PageContext pageContext, String bundle, String locale, String key)`
           Look up and return a message string, based on the specified parameters.

` String`

` message(PageContext pageContext, String bundle, String locale, String key, Object[] args)`
           Look up and return a message string, based on the specified parameters.

` String`

` pageURL(HttpServletRequest request, String page, ModuleConfig moduleConfig)`
           Return the context-relative URL that corresponds to the specified `page` attribute value, calculated based on the `pagePattern` property of the current module's [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

` boolean`

` present(PageContext pageContext, String bundle, String locale, String key)`
           Return true if a message string for the specified message key is present for the specified `Locale` and bundle.

` MessageResources`

` retrieveMessageResources(PageContext pageContext, String bundle, boolean checkPageScope)`
           Returns the appropriate MessageResources object for the current module and the given bundle.

` void`

` saveException(PageContext pageContext, Throwable exception)`
           Save the specified exception as a request attribute for later use.

`static void`

` setInstance(TagUtils instance)`
           Set the instance.

` void`

` write(PageContext pageContext, String text)`
           Write the specified text as the response to the writer associated with this page.

` void`

` writePrevious(PageContext pageContext, String text)`
           Write the specified text as the response to the writer associated with the body content for the tag within which we are currently nested.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TagUtils

    protected TagUtils()

Constructor for TagUtils.

<span id="method_detail"></span>

**Method Detail**

### getInstance

    public static TagUtils getInstance()

Returns the Singleton instance of TagUtils.

------------------------------------------------------------------------

### setInstance

    public static void setInstance(TagUtils instance)

Set the instance. This blatently violates the Singleton pattern, but then some say Singletons are an anti-pattern.

**Parameters:**  
`instance` - The instance to set.

**Since:**  
1.3.5 Changed to non-final and added setInstance() so TagUtils may be overridden, use at your own risk (you've been warned!!)

------------------------------------------------------------------------

### computeParameters

    public Map computeParameters(PageContext pageContext,
                                 String paramId,
                                 String paramName,
                                 String paramProperty,
                                 String paramScope,
                                 String name,
                                 String property,
                                 String scope,
                                 boolean transaction)
                          throws JspException

Compute a set of query parameters that will be dynamically added to a generated URL. The returned Map is keyed by parameter name, and the values are either null (no value specified), a String (single value specified), or a String[] array (multiple values specified). Parameter names correspond to the corresponding attributes of the `.html.md:link>` tag. If no query parameters are identified, return `null`.

**Parameters:**  
`pageContext` - PageContext we are operating in

`paramId` - Single-value request parameter name (if any)

`paramName` - Bean containing single-value parameter value

`paramProperty` - Property (of bean named by `paramName` containing single-value parameter value

`paramScope` - Scope containing bean named by `paramName`

`name` - Bean containing multi-value parameters Map (if any)

`property` - Property (of bean named by `name` containing multi-value parameters Map

`scope` - Scope containing bean named by `name`

`transaction` - Should we add our transaction control token?

**Returns:**  
Map of query parameters

**Throws:**  
`JspException` - if we cannot look up the required beans

`JspException` - if a class cast exception occurs on a looked-up bean or property

------------------------------------------------------------------------

### computeURL

    public String computeURL(PageContext pageContext,
                             String forward,
                             String href,
                             String page,
                             String action,
                             String module,
                             Map params,
                             String anchor,
                             boolean redirect)
                      throws MalformedURLException

**Throws:**  
`MalformedURLException`

------------------------------------------------------------------------

### computeURLWithCharEncoding

    public String computeURLWithCharEncoding(PageContext pageContext,
                                             String forward,
                                             String href,
                                             String page,
                                             String action,
                                             String module,
                                             Map params,
                                             String anchor,
                                             boolean redirect,
                                             boolean useLocalEncoding)
                                      throws MalformedURLException

Compute a hyperlink URL based on the `forward`, `href`, `action` or `page` parameter that is not null. The returned URL will have already been passed to `response.encodeURL()` for adding a session identifier.

**Parameters:**  
`pageContext` - PageContext for the tag making this call

`forward` - Logical forward name for which to look up the context-relative URI (if specified)

`href` - URL to be utilized unmodified (if specified)

`page` - Module-relative page for which a URL should be created (if specified)

`action` - Logical action name for which to look up the context-relative URI (if specified)

`params` - Map of parameters to be dynamically included (if any)

`anchor` - Anchor to be dynamically included (if any)

`redirect` - Is this URL for a `response.sendRedirect()`?

**Returns:**  
URL with session identifier

**Throws:**  
`MalformedURLException` - if a URL cannot be created for the specified parameters

------------------------------------------------------------------------

### computeURL

    public String computeURL(PageContext pageContext,
                             String forward,
                             String href,
                             String page,
                             String action,
                             String module,
                             Map params,
                             String anchor,
                             boolean redirect,
                             boolean encodeSeparator)
                      throws MalformedURLException

**Throws:**  
`MalformedURLException`

------------------------------------------------------------------------

### computeURLWithCharEncoding

    public String computeURLWithCharEncoding(PageContext pageContext,
                                             String forward,
                                             String href,
                                             String page,
                                             String action,
                                             String module,
                                             Map params,
                                             String anchor,
                                             boolean redirect,
                                             boolean encodeSeparator,
                                             boolean useLocalEncoding)
                                      throws MalformedURLException

Compute a hyperlink URL based on the `forward`, `href`, `action` or `page` parameter that is not null. The returned URL will have already been passed to `response.encodeURL()` for adding a session identifier.

**Parameters:**  
`pageContext` - PageContext for the tag making this call

`forward` - Logical forward name for which to look up the context-relative URI (if specified)

`href` - URL to be utilized unmodified (if specified)

`page` - Module-relative page for which a URL should be created (if specified)

`action` - Logical action name for which to look up the context-relative URI (if specified)

`params` - Map of parameters to be dynamically included (if any)

`anchor` - Anchor to be dynamically included (if any)

`redirect` - Is this URL for a `response.sendRedirect()`?

`encodeSeparator` - This is only checked if redirect is set to false (never encoded for a redirect). If true, query string parameter separators are encoded as \>amp;, else & is used.

`useLocalEncoding` - If set to true, urlencoding is done on the bytes of character encoding from ServletResponse\#getCharacterEncoding. Use UTF-8 otherwise.

**Returns:**  
URL with session identifier

**Throws:**  
`MalformedURLException` - if a URL cannot be created for the specified parameters

------------------------------------------------------------------------

### encodeURL

    public String encodeURL(String url)

URLencodes a string assuming the character encoding is UTF-8.

**Parameters:**  
`url` -

**Returns:**  
String The encoded url in UTF-8

------------------------------------------------------------------------

### encodeURL

    public String encodeURL(String url,
                            String enc)

Use the new URLEncoder.encode() method from Java 1.4 if available, else use the old deprecated version. This method uses reflection to find the appropriate method; if the reflection operations throw exceptions, this will return the url encoded with the old URLEncoder.encode() method.

**Parameters:**  
`enc` - The character encoding the urlencode is performed on.

**Returns:**  
String The encoded url.

------------------------------------------------------------------------

### filter

    public String filter(String value)

Filter the specified string for characters that are senstive to HTML interpreters, returning the string with these characters replaced by the corresponding character entities.

**Parameters:**  
`value` - The string to be filtered and returned

------------------------------------------------------------------------

### getActionMappingName

    public String getActionMappingName(String action)

Return the form action converted into an action mapping path. The value of the `action` property is manipulated as follows in computing the name of the requested mapping:

-   Any filename extension is removed (on the theory that extension mapping is being used to select the controller servlet).
-   If the resulting value does not start with a slash, then a slash is prepended.

------------------------------------------------------------------------

### getActionMappingURL

    public String getActionMappingURL(String action,
                                      PageContext pageContext)

Return the form action converted into a server-relative URL.

------------------------------------------------------------------------

### getActionMappingURL

    public String getActionMappingURL(String action,
                                      String module,
                                      PageContext pageContext,
                                      boolean contextRelative)

Return the form action converted into a server-relative URL.

------------------------------------------------------------------------

### getActionMessages

    public ActionMessages getActionMessages(PageContext pageContext,
                                            String paramName)
                                     throws JspException

Retrieves the value from request scope and if it isn't already an `ActionMessages`, some classes are converted to one.

**Parameters:**  
`pageContext` - The PageContext for the current page

`paramName` - Key for parameter value

**Returns:**  
ActionErrors in page context.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig(PageContext pageContext)

Return the default ModuleConfig object if it exists, null if otherwise.

**Parameters:**  
`pageContext` - The page context.

**Returns:**  
the ModuleConfig object

------------------------------------------------------------------------

### getModuleConfig

    public ModuleConfig getModuleConfig(String module,
                                        PageContext pageContext)

Return the specified ModuleConfig object for the given prefix if it exists, otherwise a NullPointerException will be thrown.

**Parameters:**  
`module` - The module prefix

`pageContext` - The page context.

**Returns:**  
the ModuleConfig object

**Throws:**  
`NullPointerException` - Thrown when module cannot be found

------------------------------------------------------------------------

### getScope

    public int getScope(String scopeName)
                 throws JspException

Converts the scope name into its corresponding PageContext constant value.

**Parameters:**  
`scopeName` - Can be "page", "request", "session", or "application" in any case.

**Returns:**  
The constant representing the scope (ie. PageContext.REQUEST\_SCOPE).

**Throws:**  
`JspException` - if the scopeName is not a valid name.

------------------------------------------------------------------------

### getUserLocale

    public Locale getUserLocale(PageContext pageContext,
                                String locale)

Look up and return current user locale, based on the specified parameters.

**Parameters:**  
`pageContext` - The PageContext associated with this request

`locale` - Name of the session attribute for our user's Locale. If this is `null`, the default locale key is used for the lookup.

**Returns:**  
current user locale

------------------------------------------------------------------------

### is.html.md

    public boolean is.html.md(PageContext pageContext)

Returns true if the custom tags are in XHTML mode.

------------------------------------------------------------------------

### lookup

    public Object lookup(PageContext pageContext,
                         String name,
                         String scopeName)
                  throws JspException

Locate and return the specified bean, from an optionally specified scope, in the specified page context. If no such bean is found, return `null` instead. If an exception is thrown, it will have already been saved via a call to `saveException()`.

**Parameters:**  
`pageContext` - Page context to be searched

`name` - Name of the bean to be retrieved

`scopeName` - Scope to be searched (page, request, session, application) or `null` to use `findAttribute()` instead

**Returns:**  
JavaBean in the specified page context

**Throws:**  
`JspException` - if an invalid scope name is requested

------------------------------------------------------------------------

### lookup

    public Object lookup(PageContext pageContext,
                         String name,
                         String property,
                         String scope)
                  throws JspException

Locate and return the specified property of the specified bean, from an optionally specified scope, in the specified page context. If an exception is thrown, it will have already been saved via a call to `saveException()`.

**Parameters:**  
`pageContext` - Page context to be searched

`name` - Name of the bean to be retrieved

`property` - Name of the property to be retrieved, or `null` to retrieve the bean itself

`scope` - Scope to be searched (page, request, session, application) or `null` to use `findAttribute()` instead

**Returns:**  
property of specified JavaBean

**Throws:**  
`JspException` - if an invalid scope name is requested

`JspException` - if the specified bean is not found

`JspException` - if accessing this property causes an IllegalAccessException, IllegalArgumentException, InvocationTargetException, or NoSuchMethodException

------------------------------------------------------------------------

### message

    public String message(PageContext pageContext,
                          String bundle,
                          String locale,
                          String key)
                   throws JspException

Look up and return a message string, based on the specified parameters.

**Parameters:**  
`pageContext` - The PageContext associated with this request

`bundle` - Name of the servlet context attribute for our message resources bundle

`locale` - Name of the session attribute for our user's Locale

`key` - Message key to be looked up and returned

**Returns:**  
message string

**Throws:**  
`JspException` - if a lookup error occurs (will have been saved in the request already)

------------------------------------------------------------------------

### message

    public String message(PageContext pageContext,
                          String bundle,
                          String locale,
                          String key,
                          Object[] args)
                   throws JspException

Look up and return a message string, based on the specified parameters.

**Parameters:**  
`pageContext` - The PageContext associated with this request

`bundle` - Name of the servlet context attribute for our message resources bundle

`locale` - Name of the session attribute for our user's Locale

`key` - Message key to be looked up and returned

`args` - Replacement parameters for this message

**Returns:**  
message string

**Throws:**  
`JspException` - if a lookup error occurs (will have been saved in the request already)

------------------------------------------------------------------------

### pageURL

    public String pageURL(HttpServletRequest request,
                          String page,
                          ModuleConfig moduleConfig)

Return the context-relative URL that corresponds to the specified `page` attribute value, calculated based on the `pagePattern` property of the current module's [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config").

**Parameters:**  
`request` - The servlet request we are processing

`page` - The module-relative URL to be substituted in to the `pagePattern` pattern for the current module (**MUST** start with a slash)

**Returns:**  
context-relative URL

------------------------------------------------------------------------

### present

    public boolean present(PageContext pageContext,
                           String bundle,
                           String locale,
                           String key)
                    throws JspException

Return true if a message string for the specified message key is present for the specified `Locale` and bundle.

**Parameters:**  
`pageContext` - The PageContext associated with this request

`bundle` - Name of the servlet context attribute for our message resources bundle

`locale` - Name of the session attribute for our user's Locale

`key` - Message key to be looked up and returned

**Returns:**  
true if a message string for message key exists

**Throws:**  
`JspException` - if a lookup error occurs (will have been saved in the request already)

------------------------------------------------------------------------

### retrieveMessageResources

    public MessageResources retrieveMessageResources(PageContext pageContext,
                                                     String bundle,
                                                     boolean checkPageScope)
                                              throws JspException

Returns the appropriate MessageResources object for the current module and the given bundle.

**Parameters:**  
`pageContext` - Search the context's scopes for the resources.

`bundle` - The bundle name to look for. If this is `null`, the default bundle name is used.

`checkPageScope` - Whether to check page scope

**Returns:**  
MessageResources The bundle's resources stored in some scope.

**Throws:**  
`JspException` - if the MessageResources object could not be found.

------------------------------------------------------------------------

### saveException

    public void saveException(PageContext pageContext,
                              Throwable exception)

Save the specified exception as a request attribute for later use.

**Parameters:**  
`pageContext` - The PageContext for the current page

`exception` - The exception to be saved

------------------------------------------------------------------------

### write

    public void write(PageContext pageContext,
                      String text)
               throws JspException

Write the specified text as the response to the writer associated with this page. **WARNING** - If you are writing body content from the `doAfterBody()` method of a custom tag class that implements `BodyTag`, you should be calling `writePrevious()` instead.

**Parameters:**  
`pageContext` - The PageContext object for this page

`text` - The text to be written

**Throws:**  
`JspException` - if an input/output error occurs (already saved)

------------------------------------------------------------------------

### writePrevious

    public void writePrevious(PageContext pageContext,
                              String text)
                       throws JspException

Write the specified text as the response to the writer associated with the body content for the tag within which we are currently nested.

**Parameters:**  
`pageContext` - The PageContext object for this page

`text` - The text to be written

**Throws:**  
`JspException` - if an input/output error occurs (already saved)

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
<td align="left"><a href="class-use/TagUtils.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/taglib/TagUtils.html"><strong>FRAMES</strong></a>    <a href="TagUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
