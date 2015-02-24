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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/TagUtils.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/tiles/taglib/util/TagUtils.html"><strong>FRAMES</strong></a>    <a href="TagUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.taglib.util
 Class TagUtils
-----------------------------------

    java.lang.Object
      org.apache.struts.tiles.taglib.util.TagUtils

------------------------------------------------------------------------

    public class TagUtils

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Collection of utilities. This class also serves as an interface between Components and Struts. If you want to rip away Struts, simply reimplement some methods in this class. You can copy them from Struts.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static boolean`

` debug`
           Debug flag

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` TagUtils()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

`static Object`

` findAttribute(String beanName, PageContext pageContext)`
           Search attribute in different contexts.

`static Object`

` getAttribute(String beanName, int scope, PageContext pageContext)`
           Get object from requested context.

`static ComponentDefinition`

` getComponentDefinition(String name, PageContext pageContext)`
           Get component definition by its name.

`static Object`

` getRealValueFromBean(String beanName, String beanProperty, String beanScope, PageContext pageContext)`
           Locate and return the specified property of the specified bean, from an optionally specified scope, in the specified page context.

`static int`

` getScope(String scopeName)`
           Converts the scope name into its corresponding PageContext constant value.

`static int`

` getScope(String scopeName, int defaultValue)`
           Get scope value from string value

`static Object`

` retrieveBean(String beanName, String scopeName, PageContext pageContext)`
           Retrieve bean from page context, using specified scope.

`static void`

` saveException(PageContext pageContext, Throwable exception)`
           Save the specified exception as a request attribute for later use.

`static void`

` setAttribute(PageContext pageContext, String name, Object beanValue)`
           Store bean in REQUEST\_SCOPE context.

`static void`

` setAttribute(PageContext pageContext, String name, Object value, String scope)`
           Store bean in requested context.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="debug"></span>

### debug

    public static final boolean debug

Debug flag

**See Also:**  
[Constant Field Values](../../../../../../constant-values.html.md#org.apache.struts.tiles.taglib.util.TagUtils.debug)

<span id="constructor_detail"></span>

**Constructor Detail**

### TagUtils

    public TagUtils()

<span id="method_detail"></span>

**Method Detail**

### getScope

    public static int getScope(String scopeName,
                               int defaultValue)
                        throws JspException

Get scope value from string value

**Parameters:**  
`scopeName` - Scope as a String.

`defaultValue` - Returned default value, if not found.

**Returns:**  
Scope as an `int`, or `defaultValue` if scope is `null`.

**Throws:**  
`JspException` - Scope name is not recognized as a valid scope.

------------------------------------------------------------------------

### getScope

    public static int getScope(String scopeName)
                        throws JspException

Converts the scope name into its corresponding PageContext constant value.

**Parameters:**  
`scopeName` - Can be "page", "request", "session", or "application" in any case.

**Returns:**  
The constant representing the scope (ie. PageContext.REQUEST\_SCOPE).

**Throws:**  
`JspException` - if the scopeName is not a valid name.

------------------------------------------------------------------------

### retrieveBean

    public static Object retrieveBean(String beanName,
                                      String scopeName,
                                      PageContext pageContext)
                               throws JspException

Retrieve bean from page context, using specified scope. If scope is not set, use `findAttribute()`.

**Parameters:**  
`beanName` - Name of bean to retrieve.

`scopeName` - Scope or `null`. If `null`, bean is searched using findAttribute().

`pageContext` - Current pageContext.

**Returns:**  
Requested bean or `null` if not found.

**Throws:**  
`JspException` - Scope name is not recognized as a valid scope.

------------------------------------------------------------------------

### findAttribute

    public static Object findAttribute(String beanName,
                                       PageContext pageContext)

Search attribute in different contexts. First, check in component context, then use pageContext.findAttribute().

**Parameters:**  
`beanName` - Name of bean to retrieve.

`pageContext` - Current pageContext.

**Returns:**  
Requested bean or `null` if not found.

------------------------------------------------------------------------

### getAttribute

    public static Object getAttribute(String beanName,
                                      int scope,
                                      PageContext pageContext)

Get object from requested context. Return `null` if not found. Context can be "component" or normal JSP contexts.

**Parameters:**  
`beanName` - Name of bean to retrieve.

`scope` - Scope from which bean must be retrieved.

`pageContext` - Current pageContext.

**Returns:**  
Requested bean or `null` if not found.

------------------------------------------------------------------------

### getRealValueFromBean

    public static Object getRealValueFromBean(String beanName,
                                              String beanProperty,
                                              String beanScope,
                                              PageContext pageContext)
                                       throws JspException

Locate and return the specified property of the specified bean, from an optionally specified scope, in the specified page context.

**Parameters:**  
`pageContext` - Page context to be searched.

`beanName` - Name of the bean to be retrieved.

`beanProperty` - Name of the property to be retrieved, or `null` to retrieve the bean itself.

`beanScope` - Scope to be searched (page, request, session, application) or `null` to use `findAttribute()` instead.

**Throws:**  
`JspException` - Scope name is not recognized as a valid scope

`JspException` - if the specified bean is not found

`JspException` - if accessing this property causes an IllegalAccessException, IllegalArgumentException, InvocationTargetException, or NoSuchMethodException

------------------------------------------------------------------------

### setAttribute

    public static void setAttribute(PageContext pageContext,
                                    String name,
                                    Object value,
                                    String scope)
                             throws JspException

Store bean in requested context. If scope is `null`, save it in REQUEST\_SCOPE context.

**Parameters:**  
`pageContext` - Current pageContext.

`name` - Name of the bean.

`scope` - Scope under which bean is saved (page, request, session, application) or `null` to store in `request()` instead.

`value` - Bean value to store.

**Throws:**  
`JspException` - Scope name is not recognized as a valid scope

------------------------------------------------------------------------

### setAttribute

    public static void setAttribute(PageContext pageContext,
                                    String name,
                                    Object beanValue)
                             throws JspException

Store bean in REQUEST\_SCOPE context.

**Parameters:**  
`pageContext` - Current pageContext.

`name` - Name of the bean.

`beanValue` - Bean value to store.

**Throws:**  
`JspException` - Scope name is not recognized as a valid scope

------------------------------------------------------------------------

### saveException

    public static void saveException(PageContext pageContext,
                                     Throwable exception)

Save the specified exception as a request attribute for later use.

**Parameters:**  
`pageContext` - The PageContext for the current page.

`exception` - The exception to be saved.

------------------------------------------------------------------------

### getComponentDefinition

    public static ComponentDefinition getComponentDefinition(String name,
                                                             PageContext pageContext)
                                                      throws JspException

Get component definition by its name.

**Parameters:**  
`name` - Definition name.

`pageContext` - The PageContext for the current page.

**Throws:**  
`JspException` - -

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
<td align="left"><a href="../../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/TagUtils.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/tiles/taglib/util/TagUtils.html"><strong>FRAMES</strong></a>    <a href="TagUtils.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
