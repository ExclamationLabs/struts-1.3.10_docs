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
<td align="left"><a href="class-use/TypeForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/validator/TypeAction.html.md" title="class in org.apache.struts.webapp.validator"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/validator/TypeForm.html"><strong>FRAMES</strong></a>    <a href="TypeForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.ValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.webapp.validator
 Class TypeForm
----------------------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          org.apache.struts.validator.ValidatorForm
              org.apache.struts.webapp.validator.TypeForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public final class TypeForm

extends [ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

Form bean for the user type page.

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.webapp.validator.TypeForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

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
| ` TypeForm()`           
                          |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getAction()`
            

` String`

` getByte()`
            

` String`

` getCreditCard()`
            

` String`

` getDate()`
            

` String`

` getDouble()`
            

` String`

` getEmail()`
            

` String`

` getFloat()`
            

` String`

` getFloatRange()`
           Float field with range checking

` String`

` getInteger()`
            

` String`

` getIntRange()`
            

` String`

` getLong()`
            

` String`

` getMask()`
            

` String`

` getMinMaxLength()`
            

` String`

` getName()`
            

` List`

` getNameList()`
            

` String[]`

` getOsList()`
            

` String`

` getOverallSatisfaction()`
            

` String`

` getSatisfaction()`
            

` String`

` getShort()`
            

` String`

` getUrl()`
            

` String[]`

` getUsedLanguages()`
            

` String`

` getWouldRecommend()`
            

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

` setAction(String action)`
            

` void`

` setByte(String sByte)`
            

` void`

` setCreditCard(String sCreditCard)`
            

` void`

` setDate(String sDate)`
            

` void`

` setDouble(String sDouble)`
            

` void`

` setEmail(String sEmail)`
            

` void`

` setFloat(String sFloat)`
            

` void`

` setFloatRange(String sFloatRange)`
           Float field with range checking

` void`

` setInteger(String sInteger)`
            

` void`

` setIntRange(String sIntRange)`
            

` void`

` setLong(String sLong)`
            

` void`

` setMask(String sMask)`
            

` void`

` setMinMaxLength(String sMinMaxLength)`
            

` void`

` setName(String name)`
            

` void`

` setNameList(List lNames)`
            

` void`

` setOsList(String[] anOsList)`
            

` void`

` setOverallSatisfaction(String anOverallSatisfaction)`
            

` void`

` setSatisfaction(String sSatisfaction)`
            

` void`

` setShort(String sShort)`
            

` void`

` setUrl(String sUrl)`
            

` void`

` setUsedLanguages(String[] anUsedLanguages)`
            

` void`

` setWouldRecommend(String anWouldRecommend)`
            

 <span id="methods_inherited_from_class_org.apache.struts.validator.ValidatorForm"></span>

| **Methods inherited from class org.apache.struts.validator.[ValidatorForm](http://struts.apache.org/apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator")** |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getPage, getResultValueMap, getValidationKey, getValidatorResults, setPage, setValidatorResults, validate`                                                                                                                        |

 <span id="methods_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Methods inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `getMultipartRequestHandler, getServlet, getServletWrapper, reset, setMultipartRequestHandler, setServlet, validate`                                                                                                |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TypeForm

    public TypeForm()

<span id="method_detail"></span>

**Method Detail**

### getAction

    public String getAction()

------------------------------------------------------------------------

### setAction

    public void setAction(String action)

------------------------------------------------------------------------

### getName

    public String getName()

------------------------------------------------------------------------

### setName

    public void setName(String name)

------------------------------------------------------------------------

### getByte

    public String getByte()

------------------------------------------------------------------------

### setByte

    public void setByte(String sByte)

------------------------------------------------------------------------

### getShort

    public String getShort()

------------------------------------------------------------------------

### setShort

    public void setShort(String sShort)

------------------------------------------------------------------------

### getInteger

    public String getInteger()

------------------------------------------------------------------------

### setInteger

    public void setInteger(String sInteger)

------------------------------------------------------------------------

### getIntRange

    public String getIntRange()

------------------------------------------------------------------------

### setIntRange

    public void setIntRange(String sIntRange)

------------------------------------------------------------------------

### getLong

    public String getLong()

------------------------------------------------------------------------

### setLong

    public void setLong(String sLong)

------------------------------------------------------------------------

### getFloat

    public String getFloat()

------------------------------------------------------------------------

### setFloat

    public void setFloat(String sFloat)

------------------------------------------------------------------------

### getFloatRange

    public String getFloatRange()

Float field with range checking

**Returns:**

------------------------------------------------------------------------

### setFloatRange

    public void setFloatRange(String sFloatRange)

Float field with range checking

**Parameters:**  
`sFloatRange` -

------------------------------------------------------------------------

### getDouble

    public String getDouble()

------------------------------------------------------------------------

### setDouble

    public void setDouble(String sDouble)

------------------------------------------------------------------------

### getDate

    public String getDate()

------------------------------------------------------------------------

### setDate

    public void setDate(String sDate)

------------------------------------------------------------------------

### getCreditCard

    public String getCreditCard()

------------------------------------------------------------------------

### setCreditCard

    public void setCreditCard(String sCreditCard)

------------------------------------------------------------------------

### getMinMaxLength

    public String getMinMaxLength()

------------------------------------------------------------------------

### setMinMaxLength

    public void setMinMaxLength(String sMinMaxLength)

------------------------------------------------------------------------

### getUrl

    public String getUrl()

------------------------------------------------------------------------

### setUrl

    public void setUrl(String sUrl)

------------------------------------------------------------------------

### getEmail

    public String getEmail()

------------------------------------------------------------------------

### setEmail

    public void setEmail(String sEmail)

------------------------------------------------------------------------

### getMask

    public String getMask()

------------------------------------------------------------------------

### setMask

    public void setMask(String sMask)

------------------------------------------------------------------------

### getSatisfaction

    public String getSatisfaction()

------------------------------------------------------------------------

### setSatisfaction

    public void setSatisfaction(String sSatisfaction)

------------------------------------------------------------------------

### getOsList

    public String[] getOsList()

------------------------------------------------------------------------

### setOsList

    public void setOsList(String[] anOsList)

------------------------------------------------------------------------

### getOverallSatisfaction

    public String getOverallSatisfaction()

------------------------------------------------------------------------

### setOverallSatisfaction

    public void setOverallSatisfaction(String anOverallSatisfaction)

------------------------------------------------------------------------

### getWouldRecommend

    public String getWouldRecommend()

------------------------------------------------------------------------

### setWouldRecommend

    public void setWouldRecommend(String anWouldRecommend)

------------------------------------------------------------------------

### getUsedLanguages

    public String[] getUsedLanguages()

------------------------------------------------------------------------

### setUsedLanguages

    public void setUsedLanguages(String[] anUsedLanguages)

------------------------------------------------------------------------

### getNameList

    public List getNameList()

------------------------------------------------------------------------

### setNameList

    public void setNameList(List lNames)

------------------------------------------------------------------------

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Reset all properties to their default values.

**Overrides:**  
`reset` in class `ValidatorForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

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
<td align="left"><a href="class-use/TypeForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/webapp/validator/TypeAction.html.md" title="class in org.apache.struts.webapp.validator"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/webapp/validator/TypeForm.html"><strong>FRAMES</strong></a>    <a href="TypeForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.validator.ValidatorForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
