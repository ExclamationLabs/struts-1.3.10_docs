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
<td align="left"><a href="class-use/PojoBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/validator/TestValidWhen.html.md" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/PojoBean.html"><strong>FRAMES</strong></a>    <a href="PojoBean.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.validator
 Class PojoBean
---------------------------

    java.lang.Object
      org.apache.struts.validator.PojoBean

------------------------------------------------------------------------

    public class PojoBean

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Test Bean class.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  PojoBean[]`

`beans`
            

`protected  Integer`

` integerValue1`
            

`protected  Integer`

` integerValue2`
            

`protected  int`

`intValue1`
            

`protected  int`

`intValue2`
            

`protected  Map`

`map`
            

`protected  String`

` stringValue1`
            

`protected  String`

` stringValue2`
            

  <span id="constructor_summary"></span>

| **Constructor Summary**                                  |
|----------------------------------------------------------|
| `PojoBean()`                                             
            Default Constructor                            |
| ` PojoBean(int intValue1, int intValue2)`                
            Construct Bean with a pair of integer values.  |
| ` PojoBean(String stringValue1, String stringValue2)`    
            Construct Bean with a pair of String values.   |

  <span id="method_summary"></span>

**Method Summary**

` PojoBean`

` getBean(int index)`
           Return and indexed Bean

` PojoBean[]`

`getBeans()`
           Return PojoBean[].

` Integer`

` getIntegerValue1()`
           Return integerValue1.

` Integer`

` getIntegerValue2()`
           Return integerValue2.

` int`

` getIntValue1()`
           Return intValue1.

` int`

` getIntValue2()`
           Return intValue2.

` Object`

`getMap()`
           Return the Map

` Object`

` getMapped(String key)`
           Set a Mapped property

` String`

` getStringValue1()`
           Return stringValue1.

` String`

` getStringValue2()`
           Return stringValue2.

` void`

` setBeans(PojoBean[] beans)`
           Set the PojoBean[].

` void`

` setIntegerValue1(Integer integerValue1)`
           Set the integerValue1.

` void`

` setIntegerValue2(Integer integerValue2)`
           Set the integerValue2.

` void`

` setIntValue1(int intValue1)`
           Set the intValue1.

` void`

` setIntValue2(int intValue2)`
           Set the intValue2.

` void`

` setMap(Map map)`
           Return the Map

` void`

` setMapped(String key, Object value)`
           Set a Mapped property

` void`

` setStringValue1(String stringValue1)`
           Set the stringValue1.

` void`

` setStringValue2(String stringValue2)`
           Set the stringValue2.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="stringValue1"></span>

### stringValue1

    protected String stringValue1

------------------------------------------------------------------------

<span id="stringValue2"></span>

### stringValue2

    protected String stringValue2

------------------------------------------------------------------------

<span id="intValue1"></span>

### intValue1

    protected int intValue1

------------------------------------------------------------------------

<span id="intValue2"></span>

### intValue2

    protected int intValue2

------------------------------------------------------------------------

<span id="integerValue1"></span>

### integerValue1

    protected Integer integerValue1

------------------------------------------------------------------------

<span id="integerValue2"></span>

### integerValue2

    protected Integer integerValue2

------------------------------------------------------------------------

<span id="beans"></span>

### beans

    protected PojoBean[] beans

------------------------------------------------------------------------

<span id="map"></span>

### map

    protected Map map

<span id="constructor_detail"></span>

**Constructor Detail**

### PojoBean

    public PojoBean()

Default Constructor

------------------------------------------------------------------------

### PojoBean

    public PojoBean(String stringValue1,
                    String stringValue2)

Construct Bean with a pair of String values.

------------------------------------------------------------------------

### PojoBean

    public PojoBean(int intValue1,
                    int intValue2)

Construct Bean with a pair of integer values.

<span id="method_detail"></span>

**Method Detail**

### setStringValue1

    public void setStringValue1(String stringValue1)

Set the stringValue1.

------------------------------------------------------------------------

### getStringValue1

    public String getStringValue1()

Return stringValue1.

------------------------------------------------------------------------

### setStringValue2

    public void setStringValue2(String stringValue2)

Set the stringValue2.

------------------------------------------------------------------------

### getStringValue2

    public String getStringValue2()

Return stringValue2.

------------------------------------------------------------------------

### setIntValue1

    public void setIntValue1(int intValue1)

Set the intValue1.

------------------------------------------------------------------------

### getIntValue1

    public int getIntValue1()

Return intValue1.

------------------------------------------------------------------------

### setIntValue2

    public void setIntValue2(int intValue2)

Set the intValue2.

------------------------------------------------------------------------

### getIntValue2

    public int getIntValue2()

Return intValue2.

------------------------------------------------------------------------

### setIntegerValue1

    public void setIntegerValue1(Integer integerValue1)

Set the integerValue1.

------------------------------------------------------------------------

### getIntegerValue1

    public Integer getIntegerValue1()

Return integerValue1.

------------------------------------------------------------------------

### setIntegerValue2

    public void setIntegerValue2(Integer integerValue2)

Set the integerValue2.

------------------------------------------------------------------------

### getIntegerValue2

    public Integer getIntegerValue2()

Return integerValue2.

------------------------------------------------------------------------

### setBeans

    public void setBeans(PojoBean[] beans)

Set the PojoBean[].

------------------------------------------------------------------------

### getBeans

    public PojoBean[] getBeans()

Return PojoBean[].

------------------------------------------------------------------------

### getBean

    public PojoBean getBean(int index)

Return and indexed Bean

------------------------------------------------------------------------

### getMap

    public Object getMap()

Return the Map

------------------------------------------------------------------------

### setMap

    public void setMap(Map map)

Return the Map

------------------------------------------------------------------------

### setMapped

    public void setMapped(String key,
                          Object value)

Set a Mapped property

------------------------------------------------------------------------

### getMapped

    public Object getMapped(String key)

Set a Mapped property

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
<td align="left"><a href="class-use/PojoBean.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> PREV CLASS   <a href="../../../../org/apache/struts/validator/TestValidWhen.html.md" title="class in org.apache.struts.validator"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/validator/PojoBean.html"><strong>FRAMES</strong></a>    <a href="PojoBean.html"><strong>NO FRAMES</strong></a>    
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
