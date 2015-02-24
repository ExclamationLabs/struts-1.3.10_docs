<span id="navbar_top"></span>

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
<td align="left"> <a href="../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

nested
------

------------------------------------------------------------------------

**Standard Syntax:**
 `     <%@ taglib prefix="nested" uri="http://struts.apache.org/tags-nested" %>`
 **XML Syntax:**
 `     <anyxmlelement xmlns:nested="http://struts.apache.org/tags-nested" />`

------------------------------------------------------------------------


    [Since Struts 1.1] 
    This tag library brings a nested context to the functionality of the Struts custom tag library. 
    It's written in a layer that extends the current Struts tags, building on their logic and functionality. The layer enables the tags to be aware of the tags which surround them so they can correctly provide the nesting property reference to the Struts system.  
    It's all about nesting beans...
     A bean holds a reference to another bean internally, and all access to that bean is handled through the current bean. This act of having one bean's access go through another bean is known as "nesting beans". The first bean is known as the parent bean. The bean which it references, is known as a child bean. The terms "parent" and "child" are commonly used to describe the model's hierarchy.  
    A simple example... 
     Take an object which represents a monkey. The monkey's job is to pick bunches of bananas. On each bunch picked hangs many bananas. If this case was translated to bean objects, the monkey object would have a reference to the bunch objects he picked, and each bunch object would hold a reference to the bananas hanging in the bunch.  
    To describe this... 
     The monkey object is the parent to the bunch object, and the bunch object is a child of the monkey object. The bunch object is parent to its child banana objects, and the child banana objects children of the bunch object. The monkey is higher in the hierarchy than the bananas, and the bananas lower in the hierarchy to the bunches.  
    One special term to remember is for the most parent class, which is known as the "root" object which starts the hierarchy. 
    Nested tags are all about efficiently managing this style of hierarchy structure within your JSP markup. 
     Important Note: Nearly all these tags extend tags from other libraries to bring their functionality into the nested context. Nesting relies on the tags working against the one bean model, and managing the properties so that they become relative to the properties they are nested within. In doing so, the tags will set the "name" attribute internally (where applicable), and in many cases will rely on the "property" attribute being set so it can be updated internally to become nested. The original tags on occasion provide options that don't use the "name" and "property" attributes. These uses will then fall outside the nested context, and will most likely cause error. To take advantage of these options, markup using the original tag for these cases. For an example see the <nested:options> tag. 

**Tag Library Information**

Display Name

*None*

Version

1.3

Short Name

nested

URI

http://struts.apache.org/tags-nested

 

**Tag Summary**

**[nest](nest.html.md)**

**Defines a new level of nesting for child tags to reference to**

This tag provides a simple method of defining a logical nesting level in the nested hierarchy. It run no explicit logic, is simply a place holder. It also means you can remove the need for explicit setting of level properties in child tags.

Just as the iterate tag provide a parent to other tags, this does the same but there is no logic for iterating or otherwise.

Example...

     <nested:write property="myNestedLevel.propertyOne" /> <nested:write property="myNestedLevel.propertyTwo" /> <nested:write property="myNestedLevel.propertyThree" /> 

Can instead become...

     <nested:nest property="myNestedLevel" > <nested:write property="propertyOne" /> <nested:write property="propertyTwo" /> <nested:write property="propertyThree" /> </nested:nest > 

**[writeNesting](writeNesting.html.md)**

**Writes or makes a scripting variable of the current nesting level.**

This tag provides a way of accessing the nested property reference used by the nested tags. Can expose a scripting variable, or simply write out the value.

**[root](root.html.md)**

**To start off a nested hierarchy without the need for a form**

This tag is provided to allow the nested tags to find a common bean reference without the need for a form and its relative overhead. As long as the `name` attribute of this tag matches the name of a bean in scope of the JSP (ie: Struts tags can find it via usual means). For example you can load a bean for use with the `jsp:useBean` tag.

The tag can also be used without specifying the `name` attribute, but this is only in the case that the current JSP is a dynamic include specified in another file. You will not be able to run the tag without a name unless this inclusion is in place. Otherwise the nested tags will not have the bean and property references that they need to provide their logic.

**Note**: The access to a bean via the `name` attribute takes priority over looking for the reference from other parent tags. So if a name is specified, a bean will have to be there waiting for it. It was made this way so that you could use separate beans within a JSP that itself is an inclusion into another.

**[define](define.html.md)**

**Nested Extension - Define a scripting variable based on the value(s) of the specified bean property.**

This tag is an extension of the `<bean:define>` tag. Please consult its documentation for information on tag attributes and usage details.

**[message](message.html.md)**

**Nested Extension - Render an internationalized message string to the response.**

This tag is an extension of the `<bean:message>` tag. Please consult its documentation for information on tag attributes and usage details.

**[size](size.html.md)**

**Nested Extension - Define a bean containing the number of elements in a Collection or Map.**

This tag is an extension of the `<bean:size>` tag. Please consult its documentation for information on tag attributes and usage details.

**[write](write.html.md)**

**Nested Extension - Render the value of the specified bean property to the current JspWriter.**

This tag is an extension of the `<bean:write>` tag. Please consult its documentation for information on tag attributes and usage details.

**[checkbox](checkbox.html.md)**

**Nested Extension - Render A Checkbox Input Field**

This tag is an extension of the `.html.md:checkbox>` tag. Please consult its documentation for information on tag attributes and usage details.

**[errors](errors.html.md)**

**Nested Extension - Conditionally display a set of accumulated error messages.**

This tag is an extension of the `.html.md:errors>` tag. Please consult its documentation for information on tag attributes and usage details.

**[file](file.html.md)**

**Nested Extension - Render A File Select Input Field**

This tag is an extension of the `.html.md:file>` tag. Please consult its documentation for information on tag attributes and usage details.

**[form](form.html.md)**

**Nested Extension - Define An Input Form**

This tag is an extension of the `.html.md:form>` tag. Please consult its documentation for information on tag attributes and usage details.

**[hidden](hidden.html.md)**

**Nested Extension - Render A Hidden Field**

This tag is an extension of the `.html.md:hidden>` tag. Please consult its documentation for information on tag attributes and usage details.

**[image](image.html.md)**

**Nested Extension - Render an input tag of type "image"**

This tag is an extension of the `.html.md:image>` tag. Please consult its documentation for information on tag attributes and usage details.

**[img](img.html.md)**

**Nested Extension - Render an HTML "img" tag**

This tag is an extension of the `.html.md:img>` tag. Please consult its documentation for information on tag attributes and usage details.

**[link](link.html.md)**

**Nested Extension - Render an HTML anchor or hyperlink**

This tag is an extension of the `.html.md:link>` tag. Please consult its documentation for information on tag attributes and usage details.

**[messages](messages.html.md)**

**Nested Extension - Conditionally display a set of accumulated messages.**

This tag is an extension of the `.html.md:messages>` tag. Please consult its documentation for information on tag attributes and usage details.

**[multibox](multibox.html.md)**

**Nested Extension - Render A Checkbox Input Field**

This tag is an extension of the `.html.md:multibox>` tag. Please consult its documentation for information on tag attributes and usage details.

**[options](options.html.md)**

**Nested Extension - Render a Collection of Select Options**

This tag is an extension of the `.html.md:options>` tag. Please consult its documentation for information on tag attributes and usage details.

**Note:** The nested context of this tag relies on the use of the "property" property, and the internal use of the "name" property. The nested tags rely on these properties and will attempt to set them itself. The `.html.md:options>` tag this tag extended allows other options for the tag which don't use these properties. To take advantage of these options, markup using the `<html:options>` tag instead of the nested tag.

For example, the "collections" option allows you to specify a separate bean reference which itself is a list of objects with properties to access the title and value parts of the.html.md option tag. You can use this in a nested context (the list is a property of a nested bean) by using the nested define tag and the original options tag.

     <nested:nest property="myNestedLevel" /> <nested:define property="collectionList" /> .html.md:options collection="collectionList" property="valueProperty" labelProperty="labelProperty" /> </nested:nest > 

**[optionsCollection](optionsCollection.html.md)**

**Nested Extension - Render a Collection of Select Options**

This tag is an extension of the `.html.md:optionsCollection>` tag. Please consult its documentation for information on tag attributes and usage details.

**[password](password.html.md)**

**Nested Extension - Render A Password Input Field**

This tag is an extension of the `.html.md:password>` tag. Please consult its documentation for information on tag attributes and usage details.

**[radio](radio.html.md)**

**Nested Extension - Render A Radio Button Input Field**

This tag is an extension of the `.html.md:radio>` tag. Please consult its documentation for information on tag attributes and usage details.

**[select](select.html.md)**

**Nested Extension - Render A Select Element**

This tag is an extension of the `.html.md:select>` tag. Please consult its documentation for information on tag attributes and usage details.

**[submit](submit.html.md)**

**Nested Extension - Render A Submit Button**

This tag is an extension of the `.html.md:submit>` tag. Please consult its documentation for information on tag attributes and usage details.

**[text](text.html.md)**

**Nested Extension - Render An Input Field of Type text**

This tag is an extension of the `.html.md:text>` tag. Please consult its documentation for information on tag attributes and usage details.

**[textarea](textarea.html.md)**

**Nested Extension - Render A Textarea**

This tag is an extension of the `.html.md:textarea>` tag. Please consult its documentation for information on tag attributes and usage details.

**[empty](empty.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is either null or an empty string.**

This tag is an extension of the `<logic:empty>` tag. Please consult its documentation for information on tag attributes and usage details.

**[equal](equal.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is equal to the specified value.**

This tag is an extension of the `<logic:equal>` tag. Please consult its documentation for information on tag attributes and usage details.

**[greaterEqual](greaterEqual.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is greater than or equal to the specified value.**

This tag is an extension of the `<logic:greaterEqual>` tag. Please consult its documentation for information on tag attributes and usage details.

**[greaterThan](greaterThan.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is greater than the specified value.**

This tag is an extension of the `<logic:greaterThan>` tag. Please consult its documentation for information on tag attributes and usage details.

**[iterate](iterate.html.md)**

**Nested Extension - Repeat the nested body content of this tag over a specified collection.**

This tag is an extension of the `<logic:iterate>` tag. Please consult its documentation for information on tag attributes and usage details.

**[lessEqual](lessEqual.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is greater than or equal to the specified value.**

This tag is an extension of the `<logic:lessEqual>` tag. Please consult its documentation for information on tag attributes and usage details.

**[lessThan](lessThan.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is less than the specified value.**

This tag is an extension of the `<logic:lessThan>` tag. Please consult its documentation for information on tag attributes and usage details.

**[match](match.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the specified value is an appropriate substring of the requested variable.**

This tag is an extension of the `<logic:match>` tag. Please consult its documentation for information on tag attributes and usage details.

**[messagesNotPresent](messagesNotPresent.html.md)**

**Nested Extension - Generate the nested body content of this tag if the specified message is not present in this request.**

This tag is an extension of the `<logic:messagesNotPresent>` tag. Please consult its documentation for information on tag attributes and usage details.

**[messagesPresent](messagesPresent.html.md)**

**Nested Extension - Generate the nested body content of this tag if the specified message is present in this request.**

This tag is an extension of the `<logic:messagesPresent>` tag. Please consult its documentation for information on tag attributes and usage details.

**[notEmpty](notEmpty.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is neither null nor an empty string.**

This tag is an extension of the `<logic:notEmpty>` tag. Please consult its documentation for information on tag attributes and usage details.

**[notEqual](notEqual.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the requested variable is not equal to the specified value.**

This tag is an extension of the `<logic:notEqual>` tag. Please consult its documentation for information on tag attributes and usage details.

**[notMatch](notMatch.html.md)**

**Nested Extension - Evaluate the nested body content of this tag if the specified value is not an appropriate substring of the requested variable.**

This tag is an extension of the `<logic:notMatch>` tag. Please consult its documentation for information on tag attributes and usage details.

**[notPresent](notPresent.html.md)**

**Nested Extension - Generate the nested body content of this tag if the specified value is not present in this request.**

This tag is an extension of the `<logic:notPresent>` tag. Please consult its documentation for information on tag attributes and usage details.

**[present](present.html.md)**

**Nested Extension - Generate the nested body content of this tag if the specified value is present in this request.**

This tag is an extension of the `<logic:present>` tag. Please consult its documentation for information on tag attributes and usage details.

  <span id="navbar_bottom"></span>

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
<td align="left"> <a href="../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">  Library  </td>
<td align="left"> Tag </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="tld-summary.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-3 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
