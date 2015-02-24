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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/UploadForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/webapp/upload/UploadAction.html.md" title="class in org.apache.struts.webapp.upload"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/upload/UploadForm.html"><strong>FRAMES</strong></a>    <a href="UploadForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.upload
 Class UploadForm
-------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm
              org.apache.struts.webapp.upload.UploadForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class UploadForm

extends [ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")

This class is a placeholder for form values. In a multipart request, files are represented by set and get methods that use the class org.apache.struts.upload.FormFile, an interface with basic methods to retrieve file information. The actual structure of the FormFile is dependant on the underlying impelementation of multipart request handling. The default implementation that struts uses is org.apache.struts.upload.CommonsMultipartRequestHandler.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.upload.UploadForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

` filePath`
           The file path to write to

`protected  String`

` queryParam`
           The value of the embedded query string parameter

`protected  FormFile`

` theFile`
           The file that the user has uploaded

`protected  String`

` theText`
           The value of the text the user has sent as form data

`protected  boolean`

` writeFile`
           Whether or not to write to a file

 <span id="fields_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Fields inherited from class org.apache.struts.validator.[ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `page, validatorResults`                                                                                                                                                                                                          |

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `multipartRequestHandler, servlet`                                                                                                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` UploadForm()`         
                          |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getFilePath()`
           Get the path to write a file to

` String`

` getQueryParam()`
           Retrieve the value of the query string parameter

` FormFile`

` getTheFile()`
           Retrieve a representation of the file the user has uploaded

` String`

` getTheText()`
           Retrieve the value of the text the user has sent as form data

` boolean`

` getWriteFile()`
           Get whether or not to write to a file

` void`

` reset()`
            

` void`

` setFilePath(String filePath)`
           Set the path to write a file to

` void`

` setQueryParam(String queryParam)`
           Set the value of the query string parameter

` void`

` setTheFile(FormFile theFile)`
           Set a representation of the file the user has uploaded

` void`

` setTheText(String theText)`
           Set the value of the form data text

` void`

` setWriteFile(boolean writeFile)`
           Set whether or not to write to a file

` ActionErrors`

` validate(ActionMapping mapping, HttpServletRequest request)`
           Check to make sure the client hasn't exceeded the maximum allowed upload size inside of this validate method.

 <span id="methods_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getPage, getResultValueMap, getValidationKey, getValidatorResults, reset, setPage, setValidatorResults`                                                                                                                           |

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getMultipartRequestHandler, getServlet, getServletWrapper, reset, setMultipartRequestHandler, setServlet, validate`                                                                                                |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="theText"></span>

### theText

    protected String theText

The value of the text the user has sent as form data

------------------------------------------------------------------------

<span id="queryParam"></span>

### queryParam

    protected String queryParam

The value of the embedded query string parameter

------------------------------------------------------------------------

<span id="writeFile"></span>

### writeFile

    protected boolean writeFile

Whether or not to write to a file

------------------------------------------------------------------------

<span id="theFile"></span>

### theFile

    protected FormFile theFile

The file that the user has uploaded

------------------------------------------------------------------------

<span id="filePath"></span>

### filePath

    protected String filePath

The file path to write to

<span id="constructor_detail"></span>

**Constructor Detail**

### UploadForm

    public UploadForm()

<span id="method_detail"></span>

**Method Detail**

### getTheText

    public String getTheText()

Retrieve the value of the text the user has sent as form data

------------------------------------------------------------------------

### setTheText

    public void setTheText(String theText)

Set the value of the form data text

------------------------------------------------------------------------

### getQueryParam

    public String getQueryParam()

Retrieve the value of the query string parameter

------------------------------------------------------------------------

### setQueryParam

    public void setQueryParam(String queryParam)

Set the value of the query string parameter

------------------------------------------------------------------------

### getTheFile

    public FormFile getTheFile()

Retrieve a representation of the file the user has uploaded

------------------------------------------------------------------------

### setTheFile

    public void setTheFile(FormFile theFile)

Set a representation of the file the user has uploaded

------------------------------------------------------------------------

### setWriteFile

    public void setWriteFile(boolean writeFile)

Set whether or not to write to a file

------------------------------------------------------------------------

### getWriteFile

    public boolean getWriteFile()

Get whether or not to write to a file

------------------------------------------------------------------------

### setFilePath

    public void setFilePath(String filePath)

Set the path to write a file to

------------------------------------------------------------------------

### getFilePath

    public String getFilePath()

Get the path to write a file to

------------------------------------------------------------------------

### reset

    public void reset()

------------------------------------------------------------------------

### validate

    public ActionErrors validate(ActionMapping mapping,
                                 HttpServletRequest request)

Check to make sure the client hasn't exceeded the maximum allowed upload size inside of this validate method.

**Overrides:**  
`validate` in class `ValidatorForm`

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/UploadForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/webapp/upload/UploadAction.html.md" title="class in org.apache.struts.webapp.upload"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/upload/UploadForm.html"><strong>FRAMES</strong></a>    <a href="UploadForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
