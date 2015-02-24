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
<td align="left"><a href="../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/SimpleActionForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../examples/simple/ProcessSimpleAction.html.md" title="class in examples.simple"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../index.html.md?examples/simple/SimpleActionForm.html"><strong>FRAMES</strong></a>    <a href="SimpleActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

examples.simple
 Class SimpleActionForm
-----------------------

    java.lang.Object
      org.apache.struts.action.ActionForm
          examples.simple.SimpleActionForm

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class SimpleActionForm

extends [ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")

A simple ActionForm

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../serialized-form.html.md#examples.simple.SimpleActionForm)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.action.ActionForm"></span>

| **Fields inherited from class org.apache.struts.action.[ActionForm](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `multipartRequestHandler, servlet`                                                                                                                                                                                 |

  <span id="constructor_summary"></span>

| **Constructor Summary**                        |
|------------------------------------------------|
| `SimpleActionForm()`                           
            Constructor for MultiboxActionForm.  |

  <span id="method_summary"></span>

**Method Summary**

` String`

`getColor()`
           Returns the color.

` boolean`

`getConfirm()`
           Returns the confirm.

` String`

`getHidden()`
           Returns the hidden.

` String`

`getMessage()`
           Returns the message.

` String`

`getName()`
           Returns the name.

` String`

`getRating()`
           Returns the rating.

` String`

`getSecret()`
           Returns the secret.

` void`

` reset(ActionMapping mapping, HttpServletRequest request)`
           Reset all properties to their default values.

` void`

` setColor(String color)`
           Sets the color.

` void`

`setConfirm(boolean confirm)`
           Sets the confirm.

` void`

` setHidden(String hidden)`
           Sets the hidden.

` void`

` setMessage(String message)`
           Sets the message.

` void`

` setName(String name)`
           Sets the name.

` void`

` setRating(String rating)`
           Sets the rating.

` void`

` setSecret(String secret)`
           Sets the secret.

` ActionErrors`

` validate(ActionMapping mapping, HttpServletRequest request)`
           Validate the properties that have been set from this HTTP request, and return an `ActionMessages` object that encapsulates any validation errors that have been found.

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

### SimpleActionForm

    public SimpleActionForm()

Constructor for MultiboxActionForm.

<span id="method_detail"></span>

**Method Detail**

### reset

    public void reset(ActionMapping mapping,
                      HttpServletRequest request)

Reset all properties to their default values.

**Overrides:**  
`reset` in class `ActionForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

------------------------------------------------------------------------

### validate

    public ActionErrors validate(ActionMapping mapping,
                                 HttpServletRequest request)

Validate the properties that have been set from this HTTP request, and return an `ActionMessages` object that encapsulates any validation errors that have been found. If no errors are found, return `null` or an `ActionMessages` object with no recorded error messages.

**Overrides:**  
`validate` in class `ActionForm`

<!-- -->

**Parameters:**  
`mapping` - The mapping used to select this instance

`request` - The servlet request we are processing

**Returns:**  
ActionMessages if any validation errors occurred

------------------------------------------------------------------------

### getColor

    public String getColor()

Returns the color.

**Returns:**  
String

------------------------------------------------------------------------

### getConfirm

    public boolean getConfirm()

Returns the confirm.

**Returns:**  
boolean

------------------------------------------------------------------------

### getHidden

    public String getHidden()

Returns the hidden.

**Returns:**  
String

------------------------------------------------------------------------

### getMessage

    public String getMessage()

Returns the message.

**Returns:**  
String

------------------------------------------------------------------------

### getName

    public String getName()

Returns the name.

**Returns:**  
String

------------------------------------------------------------------------

### getRating

    public String getRating()

Returns the rating.

**Returns:**  
String

------------------------------------------------------------------------

### getSecret

    public String getSecret()

Returns the secret.

**Returns:**  
String

------------------------------------------------------------------------

### setColor

    public void setColor(String color)

Sets the color.

**Parameters:**  
`color` - The color to set

------------------------------------------------------------------------

### setConfirm

    public void setConfirm(boolean confirm)

Sets the confirm.

**Parameters:**  
`confirm` - The confirm to set

------------------------------------------------------------------------

### setHidden

    public void setHidden(String hidden)

Sets the hidden.

**Parameters:**  
`hidden` - The hidden to set

------------------------------------------------------------------------

### setMessage

    public void setMessage(String message)

Sets the message.

**Parameters:**  
`message` - The message to set

------------------------------------------------------------------------

### setName

    public void setName(String name)

Sets the name.

**Parameters:**  
`name` - The name to set

------------------------------------------------------------------------

### setRating

    public void setRating(String rating)

Sets the rating.

**Parameters:**  
`rating` - The rating to set

------------------------------------------------------------------------

### setSecret

    public void setSecret(String secret)

Sets the secret.

**Parameters:**  
`secret` - The secret to set

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
<td align="left"><a href="../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/SimpleActionForm.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../examples/simple/ProcessSimpleAction.html.md" title="class in examples.simple"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../index.html.md?examples/simple/SimpleActionForm.html"><strong>FRAMES</strong></a>    <a href="SimpleActionForm.html"><strong>NO FRAMES</strong></a>    
<a href="../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#fields_inherited_from_class_org.apache.struts.action.ActionForm">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
