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
<td align="left"><a href="class-use/MockFormBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockEnumeration.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockHttpServletRequest.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockFormBean.html"><strong>FRAMES</strong></a>    <a href="MockFormBean.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.mock
 Class MockFormBean
----------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.mock.MockFormBean

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class MockFormBean

extends [ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")

General purpose form bean for unit tests.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:45:39 -0400 (Sat, 07 May 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.mock.MockFormBean)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  boolean`

` booleanProperty`
            

`protected  String`

` stringProperty`
            

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` multipartRequestHandler, servlet`                                                                                                                             |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                           |
|---------------------------------------------------------------------------------------------------|
| ` MockFormBean()`                                                                                 
                                                                                                    |
| ` MockFormBean(boolean throwException)`                                                           
                                                                                                    |
| ` MockFormBean(boolean throwException, boolean returnNulls)`                                      
                                                                                                    |
| ` MockFormBean(boolean throwException, boolean returnNulls, Double defaultDouble)`                
                                                                                                    |
| ` MockFormBean(boolean throwException, boolean returnNulls, String defaultValue)`                 
                                                                                                    |
| ` MockFormBean(boolean throwException, boolean returnNulls, String defaultValue, int arrayCount)` 
                                                                                                    |
| ` MockFormBean(String stringProperty)`                                                            
                                                                                                    |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` getBooleanProperty()`
            

` Double`

` getDoubleValue()`
            

` String`

` getJustThrowAnException()`
            

` Map`

` getMapProperty()`
            

` Map`

` getMapPropertyArrayValues()`
            

` String[]`

` getStringArray()`
            

` String`

` getStringProperty()`
            

` String`

` getStringValue()`
            

` Object`

` getThrowIllegalAccessException()`
            

` void`

` setBooleanProperty(boolean booleanProperty)`
            

` void`

` setStringProperty(String stringProperty)`
            

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](../../../../org/apache/struts/action/ActionForm.html.md "class in org.apache.struts.action")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getMultipartRequestHandler,  getServlet,  getServletWrapper,  reset,  reset,  setMultipartRequestHandler,  setServlet,  validate,  validate`                   |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="booleanProperty"></span>

### booleanProperty

    protected boolean booleanProperty

------------------------------------------------------------------------

<span id="stringProperty"></span>

### stringProperty

    protected String stringProperty

<span id="constructor_detail"></span>

**Constructor Detail**

### MockFormBean

    public MockFormBean()

------------------------------------------------------------------------

### MockFormBean

    public MockFormBean(boolean throwException,
                        boolean returnNulls)

------------------------------------------------------------------------

### MockFormBean

    public MockFormBean(boolean throwException)

------------------------------------------------------------------------

### MockFormBean

    public MockFormBean(boolean throwException,
                        boolean returnNulls,
                        String defaultValue)

------------------------------------------------------------------------

### MockFormBean

    public MockFormBean(String stringProperty)

------------------------------------------------------------------------

### MockFormBean

    public MockFormBean(boolean throwException,
                        boolean returnNulls,
                        String defaultValue,
                        int arrayCount)

------------------------------------------------------------------------

### MockFormBean

    public MockFormBean(boolean throwException,
                        boolean returnNulls,
                        Double defaultDouble)

<span id="method_detail"></span>

**Method Detail**

### getJustThrowAnException

    public String getJustThrowAnException()
                                   throws Exception

**Throws:**  
`Exception`

------------------------------------------------------------------------

### getThrowIllegalAccessException

    public Object getThrowIllegalAccessException()
                                          throws Exception

**Throws:**  
`Exception`

------------------------------------------------------------------------

### getStringValue

    public String getStringValue()
                          throws Exception

**Throws:**  
`Exception`

------------------------------------------------------------------------

### getStringArray

    public String[] getStringArray()
                            throws Exception

**Throws:**  
`Exception`

------------------------------------------------------------------------

### getDoubleValue

    public Double getDoubleValue()
                          throws Exception

**Throws:**  
`Exception`

------------------------------------------------------------------------

### getBooleanProperty

    public boolean getBooleanProperty()

------------------------------------------------------------------------

### setBooleanProperty

    public void setBooleanProperty(boolean booleanProperty)

------------------------------------------------------------------------

### getMapProperty

    public Map getMapProperty()

------------------------------------------------------------------------

### getMapPropertyArrayValues

    public Map getMapPropertyArrayValues()

------------------------------------------------------------------------

### getStringProperty

    public String getStringProperty()

------------------------------------------------------------------------

### setStringProperty

    public void setStringProperty(String stringProperty)

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
<td align="left"><a href="class-use/MockFormBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/mock/MockEnumeration.html.md" title="class in org.apache.struts.mock"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/mock/MockHttpServletRequest.html" title="class in org.apache.struts.mock"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/mock/MockFormBean.html"><strong>FRAMES</strong></a>    <a href="MockFormBean.html"><strong>NO FRAMES</strong></a>    
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
