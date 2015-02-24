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
<td align="left"><a href="class-use/MessageResourcesFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/MessageResources.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ModuleException.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/MessageResourcesFactory.html"><strong>FRAMES</strong></a>    <a href="MessageResourcesFactory.html"><strong>NO FRAMES</strong></a>    
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
 Class MessageResourcesFactory
------------------------------

    java.lang.Object
      org.apache.struts.util.MessageResourcesFactory

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[PropertyMessageResourcesFactory](../../../../org/apache/struts/util/PropertyMessageResourcesFactory.html.md "class in org.apache.struts.util")

------------------------------------------------------------------------

    public abstract class MessageResourcesFactory

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Factory for `MessageResources` instances. The general usage pattern for this class is:

-   Call `MessageResourcesFactory().createFactory()` to retrieve a `MessageResourcesFactory` instance.
-   Set properties as required to configure this factory instance to create `MessageResources` instances with desired characteristics.
-   Call the `createResources()` method of the factory to retrieve a newly instantiated `MessageResources` instance.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-29 23:57:50 -0400 (Mon, 29 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.util.MessageResourcesFactory)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static Class`

` clazz`
           The Java class to be used for `MessageResourcesFactory` instances.

`protected  MessageResourcesConfig`

` config`
           Configuration information for Message Resources.

`protected static String`

` factoryClass`
           The fully qualified class name to be used for `MessageResourcesFactory` instances.

`protected  boolean`

` returnNull`
           The "return null" property value to which newly created MessageResourcess should be initialized.

  <span id="constructor_summary"></span>

| **Constructor Summary**      |
|------------------------------|
| ` MessageResourcesFactory()` 
                               |

  <span id="method_summary"></span>

**Method Summary**

`static MessageResourcesFactory`

` createFactory()`
           Create and return a `MessageResourcesFactory` instance of the appropriate class, which can be used to create customized `MessageResources` instances.

`abstract  MessageResources`

` createResources(String config)`
           Create and return a newly instansiated `MessageResources`.

` MessageResourcesConfig`

` getConfig()`
           Set the configuration information for Message Resources.

`static String`

` getFactoryClass()`
           The fully qualified class name that is used for `MessageResourcesFactory` instances.

` boolean`

` getReturnNull()`
           Get default value of the "returnNull" property used to initialize newly created MessageResourcess.

` void`

` setConfig(MessageResourcesConfig config)`
           Return the configuration information for Message Resources.

`static void`

` setFactoryClass(String factoryClass)`
           Set the fully qualified class name that is used for `MessageResourcesFactory` instances.

` void`

` setReturnNull(boolean returnNull)`
           Set the default value of the "returnNull" property newly created MessageResourcess are initialized to.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="clazz"></span>

### clazz

    protected static transient Class clazz

The Java class to be used for `MessageResourcesFactory` instances.

------------------------------------------------------------------------

<span id="factoryClass"></span>

### factoryClass

    protected static String factoryClass

The fully qualified class name to be used for `MessageResourcesFactory` instances.

------------------------------------------------------------------------

<span id="config"></span>

### config

    protected MessageResourcesConfig config

Configuration information for Message Resources.

------------------------------------------------------------------------

<span id="returnNull"></span>

### returnNull

    protected boolean returnNull

The "return null" property value to which newly created MessageResourcess should be initialized.

<span id="constructor_detail"></span>

**Constructor Detail**

### MessageResourcesFactory

    public MessageResourcesFactory()

<span id="method_detail"></span>

**Method Detail**

### getConfig

    public MessageResourcesConfig getConfig()

Set the configuration information for Message Resources.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### setConfig

    public void setConfig(MessageResourcesConfig config)

Return the configuration information for Message Resources.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### getReturnNull

    public boolean getReturnNull()

Get default value of the "returnNull" property used to initialize newly created MessageResourcess.

**Returns:**  
default value of the "returnNull" property newly created MessageResourcess are initialized to.

------------------------------------------------------------------------

### setReturnNull

    public void setReturnNull(boolean returnNull)

Set the default value of the "returnNull" property newly created MessageResourcess are initialized to.

**Parameters:**  
`returnNull` - default value of the "returnNull" MessageResourcess are initialized to.

------------------------------------------------------------------------

### createResources

    public abstract MessageResources createResources(String config)

Create and return a newly instansiated `MessageResources`. This method must be implemented by concrete subclasses.

**Parameters:**  
`config` - Configuration parameter(s) for the requested bundle

------------------------------------------------------------------------

### getFactoryClass

    public static String getFactoryClass()

The fully qualified class name that is used for `MessageResourcesFactory` instances.

**Returns:**  
class name that is used for `MessageResourcesFactory` instances

------------------------------------------------------------------------

### setFactoryClass

    public static void setFactoryClass(String factoryClass)

Set the fully qualified class name that is used for `MessageResourcesFactory` instances.

**Parameters:**  
`factoryClass` - name that is used for `MessageResourcesFactory` instances

------------------------------------------------------------------------

### createFactory

    public static MessageResourcesFactory createFactory()

Create and return a `MessageResourcesFactory` instance of the appropriate class, which can be used to create customized `MessageResources` instances. If no such factory can be created, return `null` instead.

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
<td align="left"><a href="class-use/MessageResourcesFactory.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/MessageResources.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/ModuleException.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/MessageResourcesFactory.html"><strong>FRAMES</strong></a>    <a href="MessageResourcesFactory.html"><strong>NO FRAMES</strong></a>    
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
