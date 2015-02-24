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
<td align="left"><a href="../../../../../../org/apache/struts/webapp/el/exercise/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/TestBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/webapp/el/exercise/HtmlSettersAction.html.md" title="class in org.apache.struts.webapp.el.exercise"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/el/exercise/TestBean.html"><strong>FRAMES</strong></a>    <a href="TestBean.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.webapp.el.exercise
 Class TestBean
------------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.webapp.el.exercise.TestBean

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class TestBean

extends [ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")

General purpose test bean for Struts custom tag tests.

**Version:**  
$Rev: 471754 $ $Date: 2004-10-16 13:04:52 -0400 (Sat, 16 Oct 2004) $

**Author:**  
Craig R. McClanahan, Martin F N Cooper

**See Also:**  
[Serialized Form](../../../../../../serialized-form.html.md#org.apache.struts.webapp.el.exercise.TestBean)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

` String[]`

` images`
           A list of images.

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `multipartRequestHandler, servlet`                                                                                                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` TestBean()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

` Collection`

` getBeanCollection()`
            

` String[]`

` getBeanCollectionSelect()`
            

` boolean`

` getBooleanProperty()`
            

` String[]`

` getCollectionSelect()`
            

` Coord`

` getCoord(int index)`
            

` Coord[]`

` getCoords()`
            

` double`

` getDoubleProperty()`
            

` String`

` getEmptyStringProperty()`
            

` boolean`

` getFalseProperty()`
            

` float`

` getFloatProperty()`
            

` Coord`

` getImageCoord(int index)`
            

` Coord[]`

` getImageCoords()`
            

` String[]`

` getImages()`
            

` String[]`

` getIndexedStrings()`
            

` int[]`

` getIntArray()`
            

` int`

` getIntIndexed(int index)`
            

` int[]`

` getIntMultibox()`
            

` int`

` getIntProperty()`
            

` long`

` getLongProperty()`
            

` String[]`

` getMultipleSelect()`
            

` TestBean`

` getNested()`
            

` String`

` getNullProperty()`
            

` short`

` getShortProperty()`
            

` String`

` getSingleSelect()`
            

` String[]`

` getStringArray()`
            

` String`

` getStringIndexed(int index)`
            

` String[]`

` getStringMultibox()`
            

` String`

` getStringProperty()`
            

` String`

` getWithNulls()`
            

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset the properties that will be received as input.

` void`

` setBeanCollection(Collection beanCollection)`
            

` void`

` setBeanCollectionSelect(String[] beanCollectionSelect)`
            

` void`

` setBooleanProperty(boolean booleanProperty)`
            

` void`

` setCollectionSelect(String[] collectionSelect)`
            

` void`

` setCoord(int index, Coord coord)`
            

` void`

` setDoubleProperty(double doubleProperty)`
            

` void`

` setEmptyStringProperty(String emptyStringProperty)`
            

` void`

` setFalseProperty(boolean falseProperty)`
            

` void`

` setFloatProperty(float floatProperty)`
            

` void`

` setImageCoord(int index, Coord coord)`
            

` void`

` setIntArray(int[] intArray)`
            

` void`

` setIntIndexed(int index, int value)`
            

` void`

` setIntMultibox(int[] intMultibox)`
            

` void`

` setIntProperty(int intProperty)`
            

` void`

` setLongProperty(long longProperty)`
            

` void`

` setMultipleSelect(String[] multipleSelect)`
            

` void`

` setNullProperty(String nullProperty)`
            

` void`

` setShortProperty(short shortProperty)`
            

` void`

` setSingleSelect(String singleSelect)`
            

` void`

` setStringArray(String[] stringArray)`
            

` void`

` setStringIndexed(int index, String value)`
            

` void`

` setStringMultibox(String[] stringMultibox)`
            

` void`

` setStringProperty(String stringProperty)`
            

` void`

` setWithNulls(String withNulls)`
            

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getMultipartRequestHandler, getServlet, getServletWrapper, reset, setMultipartRequestHandler, setServlet, validate, validate`                                                                                      |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="images"></span>

### images

    public String[] images

A list of images.

<span id="constructor_detail"></span>

**Constructor Detail**

### TestBean

    public TestBean()

<span id="method_detail"></span>

**Method Detail**

### getBeanCollection

    public Collection getBeanCollection()

------------------------------------------------------------------------

### setBeanCollection

    public void setBeanCollection(Collection beanCollection)

------------------------------------------------------------------------

### getBeanCollectionSelect

    public String[] getBeanCollectionSelect()

------------------------------------------------------------------------

### setBeanCollectionSelect

    public void setBeanCollectionSelect(String[] beanCollectionSelect)

------------------------------------------------------------------------

### getBooleanProperty

    public boolean getBooleanProperty()

------------------------------------------------------------------------

### setBooleanProperty

    public void setBooleanProperty(boolean booleanProperty)

------------------------------------------------------------------------

### getCollectionSelect

    public String[] getCollectionSelect()

------------------------------------------------------------------------

### setCollectionSelect

    public void setCollectionSelect(String[] collectionSelect)

------------------------------------------------------------------------

### getDoubleProperty

    public double getDoubleProperty()

------------------------------------------------------------------------

### setDoubleProperty

    public void setDoubleProperty(double doubleProperty)

------------------------------------------------------------------------

### getFalseProperty

    public boolean getFalseProperty()

------------------------------------------------------------------------

### setFalseProperty

    public void setFalseProperty(boolean falseProperty)

------------------------------------------------------------------------

### getFloatProperty

    public float getFloatProperty()

------------------------------------------------------------------------

### setFloatProperty

    public void setFloatProperty(float floatProperty)

------------------------------------------------------------------------

### getIntArray

    public int[] getIntArray()

------------------------------------------------------------------------

### setIntArray

    public void setIntArray(int[] intArray)

------------------------------------------------------------------------

### getIntIndexed

    public int getIntIndexed(int index)

------------------------------------------------------------------------

### setIntIndexed

    public void setIntIndexed(int index,
                              int value)

------------------------------------------------------------------------

### getIntMultibox

    public int[] getIntMultibox()

------------------------------------------------------------------------

### setIntMultibox

    public void setIntMultibox(int[] intMultibox)

------------------------------------------------------------------------

### getIntProperty

    public int getIntProperty()

------------------------------------------------------------------------

### setIntProperty

    public void setIntProperty(int intProperty)

------------------------------------------------------------------------

### getLongProperty

    public long getLongProperty()

------------------------------------------------------------------------

### setLongProperty

    public void setLongProperty(long longProperty)

------------------------------------------------------------------------

### getMultipleSelect

    public String[] getMultipleSelect()

------------------------------------------------------------------------

### setMultipleSelect

    public void setMultipleSelect(String[] multipleSelect)

------------------------------------------------------------------------

### getNested

    public TestBean getNested()

------------------------------------------------------------------------

### getNullProperty

    public String getNullProperty()

------------------------------------------------------------------------

### setNullProperty

    public void setNullProperty(String nullProperty)

------------------------------------------------------------------------

### getShortProperty

    public short getShortProperty()

------------------------------------------------------------------------

### setShortProperty

    public void setShortProperty(short shortProperty)

------------------------------------------------------------------------

### getSingleSelect

    public String getSingleSelect()

------------------------------------------------------------------------

### setSingleSelect

    public void setSingleSelect(String singleSelect)

------------------------------------------------------------------------

### getStringArray

    public String[] getStringArray()

------------------------------------------------------------------------

### setStringArray

    public void setStringArray(String[] stringArray)

------------------------------------------------------------------------

### getStringIndexed

    public String getStringIndexed(int index)

------------------------------------------------------------------------

### setStringIndexed

    public void setStringIndexed(int index,
                                 String value)

------------------------------------------------------------------------

### getIndexedStrings

    public String[] getIndexedStrings()

------------------------------------------------------------------------

### getStringMultibox

    public String[] getStringMultibox()

------------------------------------------------------------------------

### setStringMultibox

    public void setStringMultibox(String[] stringMultibox)

------------------------------------------------------------------------

### getStringProperty

    public String getStringProperty()

------------------------------------------------------------------------

### setStringProperty

    public void setStringProperty(String stringProperty)

------------------------------------------------------------------------

### getEmptyStringProperty

    public String getEmptyStringProperty()

------------------------------------------------------------------------

### setEmptyStringProperty

    public void setEmptyStringProperty(String emptyStringProperty)

------------------------------------------------------------------------

### getCoords

    public Coord[] getCoords()

------------------------------------------------------------------------

### getCoord

    public Coord getCoord(int index)

------------------------------------------------------------------------

### setCoord

    public void setCoord(int index,
                         Coord coord)

------------------------------------------------------------------------

### getImages

    public String[] getImages()

------------------------------------------------------------------------

### getImageCoords

    public Coord[] getImageCoords()

------------------------------------------------------------------------

### getImageCoord

    public Coord getImageCoord(int index)

------------------------------------------------------------------------

### setImageCoord

    public void setImageCoord(int index,
                              Coord coord)

------------------------------------------------------------------------

### getWithNulls

    public String getWithNulls()

------------------------------------------------------------------------

### setWithNulls

    public void setWithNulls(String withNulls)

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Reset the properties that will be received as input.

**Overrides:**  
`reset` in class `ActionForm`

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
<td align="left"><a href="../../../../../../org/apache/struts/webapp/el/exercise/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/TestBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../../org/apache/struts/webapp/el/exercise/HtmlSettersAction.html.md" title="class in org.apache.struts.webapp.el.exercise"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../../index.html.md?org/apache/struts/webapp/el/exercise/TestBean.html"><strong>FRAMES</strong></a>    <a href="TestBean.html"><strong>NO FRAMES</strong></a>    
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
