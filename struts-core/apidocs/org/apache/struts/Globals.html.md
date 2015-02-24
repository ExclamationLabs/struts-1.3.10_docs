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
<td align="left"><a href="../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/Globals.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../index.html.md?org/apache/struts/Globals.html"><strong>FRAMES</strong></a>    <a href="Globals.html"><strong>NO FRAMES</strong></a>    
<a href="../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Object">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts
 Class Globals
-----------------

    java.lang.Object
      org.apache.struts.Globals

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class Globals

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Global manifest constants for the entire Struts Framework.

**Version:**  
$Rev: 471754 $ $Date: 2005-06-18 20:27:26 -0400 (Sat, 18 Jun 2005) $

**See Also:**  
[Serialized Form](../../../serialized-form.html.md#org.apache.struts.Globals)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

`ACTION_SERVLET_KEY`
           The context attributes key under which our `ActionServlet` instance will be stored.

`static String`

`CANCEL_KEY`
           The request attributes key under which a boolean `true` value should be stored if this request was cancelled.

`static String`

`CANCEL_PROPERTY`
           The property under which a Cancel button press is reported.

`static String`

`CANCEL_PROPERTY_X`
           The property under which a Cancel button press is reported, if the Cancel button is rendered as an image.

`static String`

`ERROR_KEY`
           The request attributes key under which your action should store an `org.apache.struts.action.ActionErrors` object, if you are using the corresponding custom tag library elements.

`static String`

`EXCEPTION_KEY`
           The request attributes key under which Struts custom tags might store a `Throwable` that caused them to report a JspException at runtime.

`static String`

`LOCALE_KEY`
           The session attributes key under which the user's selected `java.util.Locale` is stored, if any.

`static String`

`MAPPING_KEY`
           The request attributes key under which our `org.apache.struts.ActionMapping` instance is passed.

`static String`

`MESSAGE_KEY`
           The request attributes key under which your action should store an `org.apache.struts.action.ActionMessages` object, if you are using the corresponding custom tag library elements.

`static String`

`MESSAGES_KEY`
           The base of the context attributes key under which our module `MessageResources` will be stored.

`static String`

`MODULE_KEY`
           The base of the context attributes key under which our `ModuleConfig` data structure will be stored.

`static String`

`MODULE_PREFIXES_KEY`
           The ServletContext attribute under which we store the module prefixes String[].

`static String`

`MULTIPART_KEY`
           The request attributes key under which our multipart class is stored.

`static String`

`ORIGINAL_URI_KEY`
           The request attribute under which we store the original URI of the request.

`static String`

`PLUG_INS_KEY`
           The base of the context attributes key under which an array of `PlugIn` instances will be stored.

`static String`

`REQUEST_PROCESSOR_KEY`
           The base of the context attributes key under which our `RequestProcessor` instance will be stored.

`static String`

`SERVLET_KEY`
           The context attributes key under which we store the mapping defined for our controller serlet, which will be either a path-mapped pattern (`/action/*`) or an extension mapped pattern (`*.do`).

`static String`

`TAGLIB_PACKAGE`
           The name of the taglib package.

`static String`

`TOKEN_KEY`
           The property under which a transaction token is reported.

`static String`

`TRANSACTION_TOKEN_KEY`
           The session attributes key under which our transaction token is stored, if it is used.

`static String`

`XHTML_KEY`
           The page attributes key under which .html.md status is stored.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| `Globals()`             
                          |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="ACTION_SERVLET_KEY"></span>

### ACTION\_SERVLET\_KEY

    public static final String ACTION_SERVLET_KEY

The context attributes key under which our `ActionServlet` instance will be stored.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.ACTION_SERVLET_KEY)

------------------------------------------------------------------------

<span id="CANCEL_KEY"></span>

### CANCEL\_KEY

    public static final String CANCEL_KEY

The request attributes key under which a boolean `true` value should be stored if this request was cancelled.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.CANCEL_KEY)

------------------------------------------------------------------------

<span id="MODULE_KEY"></span>

### MODULE\_KEY

    public static final String MODULE_KEY

The base of the context attributes key under which our `ModuleConfig` data structure will be stored. This will be suffixed with the actual module prefix (including the leading "/" character) to form the actual attributes key.

For each request processed by the controller servlet, the `ModuleConfig` object for the module selected by the request URI currently being processed will also be exposed under this key as a request attribute.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.MODULE_KEY)

------------------------------------------------------------------------

<span id="MODULE_PREFIXES_KEY"></span>

### MODULE\_PREFIXES\_KEY

    public static final String MODULE_PREFIXES_KEY

The ServletContext attribute under which we store the module prefixes String[].

**Since:**  
Struts 1.2

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.MODULE_PREFIXES_KEY)

------------------------------------------------------------------------

<span id="ORIGINAL_URI_KEY"></span>

### ORIGINAL\_URI\_KEY

    public static final String ORIGINAL_URI_KEY

The request attribute under which we store the original URI of the request.

**Since:**  
Struts 1.3

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.ORIGINAL_URI_KEY)

------------------------------------------------------------------------

<span id="ERROR_KEY"></span>

### ERROR\_KEY

    public static final String ERROR_KEY

The request attributes key under which your action should store an `org.apache.struts.action.ActionErrors` object, if you are using the corresponding custom tag library elements.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.ERROR_KEY)

------------------------------------------------------------------------

<span id="EXCEPTION_KEY"></span>

### EXCEPTION\_KEY

    public static final String EXCEPTION_KEY

The request attributes key under which Struts custom tags might store a `Throwable` that caused them to report a JspException at runtime. This value can be used on an error page to provide more detailed information about what really went wrong.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.EXCEPTION_KEY)

------------------------------------------------------------------------

<span id="LOCALE_KEY"></span>

### LOCALE\_KEY

    public static final String LOCALE_KEY

The session attributes key under which the user's selected `java.util.Locale` is stored, if any. If no such attribute is found, the system default locale will be used when retrieving internationalized messages. If used, this attribute is typically set during user login processing.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.LOCALE_KEY)

------------------------------------------------------------------------

<span id="MAPPING_KEY"></span>

### MAPPING\_KEY

    public static final String MAPPING_KEY

The request attributes key under which our `org.apache.struts.ActionMapping` instance is passed.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.MAPPING_KEY)

------------------------------------------------------------------------

<span id="MESSAGE_KEY"></span>

### MESSAGE\_KEY

    public static final String MESSAGE_KEY

The request attributes key under which your action should store an `org.apache.struts.action.ActionMessages` object, if you are using the corresponding custom tag library elements.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.MESSAGE_KEY)

------------------------------------------------------------------------

<span id="MESSAGES_KEY"></span>

### MESSAGES\_KEY

    public static final String MESSAGES_KEY

The base of the context attributes key under which our module `MessageResources` will be stored. This will be suffixed with the actual module prefix (including the leading "/" character) to form the actual resources key.

For each request processed by the controller servlet, the `MessageResources` object for the module selected by the request URI currently being processed will also be exposed under this key as a request attribute.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.MESSAGES_KEY)

------------------------------------------------------------------------

<span id="MULTIPART_KEY"></span>

### MULTIPART\_KEY

    public static final String MULTIPART_KEY

The request attributes key under which our multipart class is stored.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.MULTIPART_KEY)

------------------------------------------------------------------------

<span id="PLUG_INS_KEY"></span>

### PLUG\_INS\_KEY

    public static final String PLUG_INS_KEY

The base of the context attributes key under which an array of `PlugIn` instances will be stored. This will be suffixed with the actual module prefix (including the leading "/" character) to form the actual attributes key.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.PLUG_INS_KEY)

------------------------------------------------------------------------

<span id="REQUEST_PROCESSOR_KEY"></span>

### REQUEST\_PROCESSOR\_KEY

    public static final String REQUEST_PROCESSOR_KEY

The base of the context attributes key under which our `RequestProcessor` instance will be stored. This will be suffixed with the actual module prefix (including the leading "/" character) to form the actual attributes key.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.REQUEST_PROCESSOR_KEY)

------------------------------------------------------------------------

<span id="SERVLET_KEY"></span>

### SERVLET\_KEY

    public static final String SERVLET_KEY

The context attributes key under which we store the mapping defined for our controller serlet, which will be either a path-mapped pattern (`/action/*`) or an extension mapped pattern (`*.do`).

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.SERVLET_KEY)

------------------------------------------------------------------------

<span id="TRANSACTION_TOKEN_KEY"></span>

### TRANSACTION\_TOKEN\_KEY

    public static final String TRANSACTION_TOKEN_KEY

The session attributes key under which our transaction token is stored, if it is used.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.TRANSACTION_TOKEN_KEY)

------------------------------------------------------------------------

<span id="XHTML_KEY"></span>

### XHTML\_KEY

    public static final String XHTML_KEY

The page attributes key under which .html.md status is stored. This may be "true" or "false". When set to true, the html tags output xhtml.

**Since:**  
Struts 1.1

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.XHTML_KEY)

------------------------------------------------------------------------

<span id="TAGLIB_PACKAGE"></span>

### TAGLIB\_PACKAGE

    public static final String TAGLIB_PACKAGE

The name of the taglib package.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.TAGLIB_PACKAGE)

------------------------------------------------------------------------

<span id="CANCEL_PROPERTY"></span>

### CANCEL\_PROPERTY

    public static final String CANCEL_PROPERTY

The property under which a Cancel button press is reported.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.CANCEL_PROPERTY)

------------------------------------------------------------------------

<span id="CANCEL_PROPERTY_X"></span>

### CANCEL\_PROPERTY\_X

    public static final String CANCEL_PROPERTY_X

The property under which a Cancel button press is reported, if the Cancel button is rendered as an image.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.CANCEL_PROPERTY_X)

------------------------------------------------------------------------

<span id="TOKEN_KEY"></span>

### TOKEN\_KEY

    public static final String TOKEN_KEY

The property under which a transaction token is reported.

**See Also:**  
[Constant Field Values](../../../constant-values.html.md#org.apache.struts.Globals.TOKEN_KEY)

<span id="constructor_detail"></span>

**Constructor Detail**

### Globals

    public Globals()

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
<td align="left"><a href="../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/Globals.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../index.html.md?org/apache/struts/Globals.html"><strong>FRAMES</strong></a>    <a href="Globals.html"><strong>NO FRAMES</strong></a>    
<a href="../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
