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
<td align="left"><a href="class-use/ControllerConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ConfigRuleSet.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ExceptionConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ControllerConfig.html"><strong>FRAMES</strong></a>    <a href="ControllerConfig.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Class ControllerConfig
------------------------

    java.lang.Object
      org.apache.struts.config.BaseConfig
          org.apache.struts.config.ControllerConfig

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class ControllerConfig

extends [BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")

A JavaBean representing the configuration information of a `<controller>` element in a Struts configuration file.

**Since:**  
Struts 1.1

**Version:**  
$Rev: 471754 $ $Date: 2005-05-12 18:41:19 -0400 (Thu, 12 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.config.ControllerConfig)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  int`

` bufferSize`
            The input buffer size for file uploads.

`protected  String`

` catalog`
            The chain catalog name for this module.

`protected  String`

` command`
            The chain command to execute for each request.

`protected  String`

` contentType`
            The content type and character encoding to be set on each response.

`protected  String`

` forwardPattern`
           The replacement pattern used to determine a context-relative URL from a [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") element.

`protected  boolean`

` inputForward`
           Should the `input` property of [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") instances associated with this module be treated as the name of a corresponding [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config").

`protected  boolean`

` locale`
            Should we store a Locale object in the user's session if needed?

`protected  String`

` maxFileSize`
            The maximum file size to process for file uploads.

`protected  String`

` memFileSize`
            The maximum file size to retain in memory.

`protected  String`

` multipartClass`
            The fully qualified Java class name of the MultipartRequestHandler class to be used.

`protected  boolean`

` nocache`
            Should we set no-cache HTTP headers on each response?

`protected  String`

` pagePattern`
           The replacement pattern used to determine a context-relative URL from the `page` attribute of Struts tags and configuration properties.

`protected  String`

` processorClass`
            The fully qualified class name of the RequestProcessor implementation class to be used for this module.

`protected  String`

` tempDir`
            The temporary working directory to use for file uploads.

 <span id="fields_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Fields inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `configured`                                                                                                                                                    |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ControllerConfig()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

` int`

` getBufferSize()`
            

` String`

` getCatalog()`
            

` String`

` getCommand()`
            

` String`

` getContentType()`
            

` String`

` getForwardPattern()`
            

` boolean`

` getInputForward()`
            

` boolean`

` getLocale()`
            

` String`

` getMaxFileSize()`
            

` String`

` getMemFileSize()`
            

` String`

` getMultipartClass()`
            

` boolean`

` getNocache()`
            

` String`

` getPagePattern()`
            

` String`

` getProcessorClass()`
            

` String`

` getTempDir()`
            

` void`

` setBufferSize(int bufferSize)`
            

` void`

` setCatalog(String catalog)`
            

` void`

` setCommand(String command)`
            

` void`

` setContentType(String contentType)`
            

` void`

` setForwardPattern(String forwardPattern)`
            

` void`

` setInputForward(boolean inputForward)`
            

` void`

` setLocale(boolean locale)`
            

` void`

` setMaxFileSize(String maxFileSize)`
            

` void`

` setMemFileSize(String memFileSize)`
            

` void`

` setMultipartClass(String multipartClass)`
            

` void`

` setNocache(boolean nocache)`
            

` void`

` setPagePattern(String pagePattern)`
            

` void`

` setProcessorClass(String processorClass)`
            

` void`

` setTempDir(String tempDir)`
            

` String`

` toString()`
            Return a String representation of this object.

 <span id="methods_inherited_from_class_org.apache.struts.config.BaseConfig"></span>

| **Methods inherited from class org.apache.struts.config.[BaseConfig](../../../../org/apache/struts/config/BaseConfig.html.md "class in org.apache.struts.config")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` copyProperties, freeze,  getProperties,  getProperty,  inheritProperties,  setProperties,  setProperty,  throwIfConfigured`                                    |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="bufferSize"></span>

### bufferSize

    protected int bufferSize

The input buffer size for file uploads.

------------------------------------------------------------------------

<span id="contentType"></span>

### contentType

    protected String contentType

The content type and character encoding to be set on each response.

------------------------------------------------------------------------

<span id="catalog"></span>

### catalog

    protected String catalog

The chain catalog name for this module.

------------------------------------------------------------------------

<span id="command"></span>

### command

    protected String command

The chain command to execute for each request.

------------------------------------------------------------------------

<span id="forwardPattern"></span>

### forwardPattern

    protected String forwardPattern

The replacement pattern used to determine a context-relative URL from a [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") element. The pattern may consist of any combination of the following markers and characters:

-   `$M` - Replaced by the module prefix for the current module.
-   `$P` - Replaced by the `path` property of a [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html.md "class in org.apache.struts.config") instance.
-   `$$` - Renders a literal dollar sign ("$") character in the resulting URL.
-   A dollar sign followed by any other character is reserved for future use, and both characters are silently swallowed.
-   All other characters in the pattern are passed through unchanged.

If this property is set to `null`, a default pattern of `$M$P` is utilized, which is backwards compatible with the hard coded functionality in prior versions.

------------------------------------------------------------------------

<span id="inputForward"></span>

### inputForward

    protected boolean inputForward

Should the `input` property of [`ActionConfig`](../../../../org/apache/struts/config/ActionConfig.html.md "class in org.apache.struts.config") instances associated with this module be treated as the name of a corresponding [`ForwardConfig`](../../../../org/apache/struts/config/ForwardConfig.html "class in org.apache.struts.config"). A `false` value treats them as a module-relative path (consistent with the hard coded behavior of earlier versions of Struts.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="locale"></span>

### locale

    protected boolean locale

Should we store a Locale object in the user's session if needed?

------------------------------------------------------------------------

<span id="maxFileSize"></span>

### maxFileSize

    protected String maxFileSize

The maximum file size to process for file uploads.

------------------------------------------------------------------------

<span id="memFileSize"></span>

### memFileSize

    protected String memFileSize

The maximum file size to retain in memory.

------------------------------------------------------------------------

<span id="multipartClass"></span>

### multipartClass

    protected String multipartClass

The fully qualified Java class name of the MultipartRequestHandler class to be used.

------------------------------------------------------------------------

<span id="nocache"></span>

### nocache

    protected boolean nocache

Should we set no-cache HTTP headers on each response?

------------------------------------------------------------------------

<span id="pagePattern"></span>

### pagePattern

    protected String pagePattern

The replacement pattern used to determine a context-relative URL from the `page` attribute of Struts tags and configuration properties. The pattern may consist of any combination of the following markers and characters:

-   `$M` - Replaced by the module prefix for the current module.
-   `$P` - Replaced by the `page` attribute value being evaluated.
-   `$$` - Renders a literal dollar sign ("$") character in the resulting URL.
-   A dollar sign followed by any other character is reserved for future use, and both characters are silently swallowed.
-   All other characters in the pattern are passed through unchanged.

If this property is set to `null`, a default pattern of `$M$P` is utilized, which is backwards compatible with the hard coded functionality in prior versions.

------------------------------------------------------------------------

<span id="processorClass"></span>

### processorClass

    protected String processorClass

The fully qualified class name of the RequestProcessor implementation class to be used for this module.

------------------------------------------------------------------------

<span id="tempDir"></span>

### tempDir

    protected String tempDir

The temporary working directory to use for file uploads.

<span id="constructor_detail"></span>

**Constructor Detail**

### ControllerConfig

    public ControllerConfig()

<span id="method_detail"></span>

**Method Detail**

### getBufferSize

    public int getBufferSize()

------------------------------------------------------------------------

### setBufferSize

    public void setBufferSize(int bufferSize)

------------------------------------------------------------------------

### getContentType

    public String getContentType()

------------------------------------------------------------------------

### setContentType

    public void setContentType(String contentType)

------------------------------------------------------------------------

### getCatalog

    public String getCatalog()

------------------------------------------------------------------------

### setCatalog

    public void setCatalog(String catalog)

------------------------------------------------------------------------

### getCommand

    public String getCommand()

------------------------------------------------------------------------

### setCommand

    public void setCommand(String command)

------------------------------------------------------------------------

### getForwardPattern

    public String getForwardPattern()

------------------------------------------------------------------------

### setForwardPattern

    public void setForwardPattern(String forwardPattern)

------------------------------------------------------------------------

### getInputForward

    public boolean getInputForward()

------------------------------------------------------------------------

### setInputForward

    public void setInputForward(boolean inputForward)

------------------------------------------------------------------------

### getLocale

    public boolean getLocale()

------------------------------------------------------------------------

### setLocale

    public void setLocale(boolean locale)

------------------------------------------------------------------------

### getMaxFileSize

    public String getMaxFileSize()

------------------------------------------------------------------------

### setMaxFileSize

    public void setMaxFileSize(String maxFileSize)

------------------------------------------------------------------------

### getMemFileSize

    public String getMemFileSize()

------------------------------------------------------------------------

### setMemFileSize

    public void setMemFileSize(String memFileSize)

------------------------------------------------------------------------

### getMultipartClass

    public String getMultipartClass()

------------------------------------------------------------------------

### setMultipartClass

    public void setMultipartClass(String multipartClass)

------------------------------------------------------------------------

### getNocache

    public boolean getNocache()

------------------------------------------------------------------------

### setNocache

    public void setNocache(boolean nocache)

------------------------------------------------------------------------

### getPagePattern

    public String getPagePattern()

------------------------------------------------------------------------

### setPagePattern

    public void setPagePattern(String pagePattern)

------------------------------------------------------------------------

### getProcessorClass

    public String getProcessorClass()

------------------------------------------------------------------------

### setProcessorClass

    public void setProcessorClass(String processorClass)

------------------------------------------------------------------------

### getTempDir

    public String getTempDir()

------------------------------------------------------------------------

### setTempDir

    public void setTempDir(String tempDir)

------------------------------------------------------------------------

### toString

    public String toString()

Return a String representation of this object.

**Overrides:**  
`toString` in class `Object`

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
<td align="left"><a href="class-use/ControllerConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/ConfigRuleSet.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/ExceptionConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/ControllerConfig.html"><strong>FRAMES</strong></a>    <a href="ControllerConfig.html"><strong>NO FRAMES</strong></a>    
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
