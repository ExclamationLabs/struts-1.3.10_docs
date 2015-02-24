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
<td align="left"><a href="class-use/Constants.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/chain/ComposableRequestProcessor.html.md" title="class in org.apache.struts.chain"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/chain/Constants.html"><strong>FRAMES</strong></a>    <a href="Constants.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Object">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.chain
 Class Constants
-----------------------

    java.lang.Object
      org.apache.struts.chain.Constants

------------------------------------------------------------------------

    public final class Constants

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Global constants for the Chain of Responsibility Library.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` ACTION_CONFIG_KEY`
           The default context attribute under which the ActionConfig for the current request will be stored.

`static String`

` ACTION_FORM_KEY`
           The default context attribute under which the ActionForm for the current request will be stored.

`static String`

`ACTION_KEY`
           The default context attribute under which the Action for the current request will be stored.

`static String`

` ACTION_SERVLET_KEY`
           The default context attribute under which the ActionServet for the current application will be stored.

`static String`

`ACTIONS_KEY`
           The base part of the context attribute under which a Map containing the Action instances associated with this module are stored.

`static String`

`CANCEL_KEY`
           The default context attribute under which a boolean flag indicating whether this request has been cancelled will be stored.

`static String`

`CATALOG_ATTR`
           The context attribute under which the Catalog containing our defined command chains has been stored.

`static String`

`EXCEPTION_KEY`
           The default context attribute under which an Exception will be stored before passing it to an exception handler chain.

`static String`

` FORWARD_CONFIG_KEY`
           The default context attribute under which the ForwardConfig for the current request will be stored.

`static String`

`INCLUDE_KEY`
           The default context attribute under which the include path for the current request will be stored.

`static String`

` INCLUDE_PATH_INFO`
           The request attribute under which the path information is stored for processing during a RequestDispatcher.include() call.

`static String`

` INCLUDE_SERVLET_PATH`
           The request attribute under which the servlet path is stored for processing during a RequestDispatcher.include() call.

`static String`

`LOCALE_KEY`
           The default context attribute under which the Locale for the current request will be stored.

`static String`

` MESSAGE_RESOURCES_KEY`
           The default context attribute under which the MessageResources for the current request will be stored.

`static String`

` MODULE_CONFIG_KEY`
           The default context attribute under which the ModuleConfig for the current request will be stored.

`static String`

`VALID_KEY`
           The default context attribute key under which a Boolean is stored, indicating the valid state of the current request.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| `Constants()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="ACTION_KEY"></span>

### ACTION\_KEY

    public static final String ACTION_KEY

The default context attribute under which the Action for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.ACTION_KEY)

------------------------------------------------------------------------

<span id="ACTION_CONFIG_KEY"></span>

### ACTION\_CONFIG\_KEY

    public static final String ACTION_CONFIG_KEY

The default context attribute under which the ActionConfig for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.ACTION_CONFIG_KEY)

------------------------------------------------------------------------

<span id="ACTION_FORM_KEY"></span>

### ACTION\_FORM\_KEY

    public static final String ACTION_FORM_KEY

The default context attribute under which the ActionForm for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.ACTION_FORM_KEY)

------------------------------------------------------------------------

<span id="ACTION_SERVLET_KEY"></span>

### ACTION\_SERVLET\_KEY

    public static final String ACTION_SERVLET_KEY

The default context attribute under which the ActionServet for the current application will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.ACTION_SERVLET_KEY)

------------------------------------------------------------------------

<span id="CANCEL_KEY"></span>

### CANCEL\_KEY

    public static final String CANCEL_KEY

The default context attribute under which a boolean flag indicating whether this request has been cancelled will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.CANCEL_KEY)

------------------------------------------------------------------------

<span id="EXCEPTION_KEY"></span>

### EXCEPTION\_KEY

    public static final String EXCEPTION_KEY

The default context attribute under which an Exception will be stored before passing it to an exception handler chain.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.EXCEPTION_KEY)

------------------------------------------------------------------------

<span id="FORWARD_CONFIG_KEY"></span>

### FORWARD\_CONFIG\_KEY

    public static final String FORWARD_CONFIG_KEY

The default context attribute under which the ForwardConfig for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.FORWARD_CONFIG_KEY)

------------------------------------------------------------------------

<span id="INCLUDE_KEY"></span>

### INCLUDE\_KEY

    public static final String INCLUDE_KEY

The default context attribute under which the include path for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.INCLUDE_KEY)

------------------------------------------------------------------------

<span id="LOCALE_KEY"></span>

### LOCALE\_KEY

    public static final String LOCALE_KEY

The default context attribute under which the Locale for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.LOCALE_KEY)

------------------------------------------------------------------------

<span id="MESSAGE_RESOURCES_KEY"></span>

### MESSAGE\_RESOURCES\_KEY

    public static final String MESSAGE_RESOURCES_KEY

The default context attribute under which the MessageResources for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.MESSAGE_RESOURCES_KEY)

------------------------------------------------------------------------

<span id="MODULE_CONFIG_KEY"></span>

### MODULE\_CONFIG\_KEY

    public static final String MODULE_CONFIG_KEY

The default context attribute under which the ModuleConfig for the current request will be stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.MODULE_CONFIG_KEY)

------------------------------------------------------------------------

<span id="VALID_KEY"></span>

### VALID\_KEY

    public static final String VALID_KEY

The default context attribute key under which a Boolean is stored, indicating the valid state of the current request. If not present, a value of Boolean.FALSE should be assumed.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.VALID_KEY)

------------------------------------------------------------------------

<span id="ACTIONS_KEY"></span>

### ACTIONS\_KEY

    public static final String ACTIONS_KEY

The base part of the context attribute under which a Map containing the Action instances associated with this module are stored. This value must be suffixed with the module prefix in order to create a unique key per module.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.ACTIONS_KEY)

------------------------------------------------------------------------

<span id="CATALOG_ATTR"></span>

### CATALOG\_ATTR

    public static final String CATALOG_ATTR

The context attribute under which the Catalog containing our defined command chains has been stored.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.CATALOG_ATTR)

------------------------------------------------------------------------

<span id="INCLUDE_PATH_INFO"></span>

### INCLUDE\_PATH\_INFO

    public static final String INCLUDE_PATH_INFO

The request attribute under which the path information is stored for processing during a RequestDispatcher.include() call.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.INCLUDE_PATH_INFO)

------------------------------------------------------------------------

<span id="INCLUDE_SERVLET_PATH"></span>

### INCLUDE\_SERVLET\_PATH

    public static final String INCLUDE_SERVLET_PATH

The request attribute under which the servlet path is stored for processing during a RequestDispatcher.include() call.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.chain.Constants.INCLUDE_SERVLET_PATH)

<span id="constructor_detail"></span>

**Constructor Detail**

### Constants

    public Constants()

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
<td align="left"><a href="class-use/Constants.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/chain/ComposableRequestProcessor.html.md" title="class in org.apache.struts.chain"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/chain/Constants.html"><strong>FRAMES</strong></a>    <a href="Constants.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Object">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
