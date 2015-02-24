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
<td align="left"> <a href="tld-summary.html.md"><strong>Library</strong></a> </td>
<td align="left">  Tag  </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="define.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

bean
 Tag define
-----------

------------------------------------------------------------------------

**Define a scripting variable based on the value(s) of the specified bean property.**

Create a new attribute (in the scope specified by the `toScope` property, if any), and a corresponding scripting variable, both of which are named by the value of the `id` attribute. The corresponding value to which this new attribute (and scripting variable) is set are specified via use of exactly one of the following approaches (trying to use more than one will result in a JspException being thrown):

-   Specify a `name` attribute (plus optional `property` and `scope` attributes) - The created attribute and scripting variable will be of the type of the retrieved JavaBean property, unless it is a Java primitive type, in which case it will be wrapped in the appropriate wrapper class (i.e. int is wrapped by java.lang.Integer).
-   Specify a `value` attribute - The created attribute and scripting variable will be of type `java.lang.String`, set to the value of this attribute.
-   Specify nested body content - The created attribute and scripting variable will be of type `java.lang.String`, set to the value of the nested body content.

If a problem occurs while retrieving the specified bean property, a request time exception will be thrown.

The `<bean:define>` tag differs from `<jsp:useBean>` in several ways, including:

-   Unconditionally creates (or replaces) a bean under the specified identifier.
-   Can create a bean with the value returned by a property getter of a different bean (including properties referenced with a nested and/or indexed property name).
-   Can create a bean whose contents is a literal string (or the result of a runtime expression) specified by the `value` attribute.
-   Does not support nested content (such as `<jsp:setProperty>` tags) that are only executed if a bean was actually created.

**USAGE NOTE** - There is a restriction in the JSP 1.1 Specification that disallows using the same value for an `id` attribute more than once in a single JSP page. Therefore, you will not be able to use `<bean:define>` for the same bean name more than once in a single page.

**USAGE NOTE** - If you use another tag to create the body content (e.g. bean:write), that tag must return a non-empty String. An empty String equates to an empty body or a null String, and a new scripting variable cannot be defined as null. Your bean must return a non-empty String, or the define tag must be wrapped within a logic tag to test for an empty or null value.

**USAGE NOTE** - You cannot use bean:define to **instantiate** a DynaActionForm (type="org.apache.struts.action.DynaActionForm") with the properties specified in the struts-config. The mechanics of creating the dyna-properties is complex and cannot be handled by a no-argument constructor. If you need to create an ActionForm this way, you must use a conventional ActionForm.

See the Bean Developer's Guide section on [bean creation](../apidocs/org/apache/struts/taglib/bean/package-summary.html.md#doc.Creation) for more information about these differences, as well as alternative approaches to introducing beans into a JSP page.

------------------------------------------------------------------------

**Tag Information**

Tag Class

org.apache.struts.taglib.bean.DefineTag

TagExtraInfo Class

org.apache.struts.taglib.bean.DefineTei

Body Content

JSP

Display Name

*None*

**Attributes**

**Name**

**Required**

**Request-time**

**Type**

**Description**

id

true

false

`java.lang.String`

Specifies the name of the scripting variable (and associated page scope attribute) that will be made available with the value of the specified property.

name

false

true

`java.lang.String`

Specifies the attribute name of the bean whose property is accessed to define a new page scope attribute (if `property` is also specified) or the attribute name of the bean that is duplicated with the new reference created by this tag (if `property` is not also specified). This attribute is required unless you specify a `value` attribute or nested body content.

property

false

true

`java.lang.String`

Specifies the name of the property to be accessed on the bean specified by `name`. This value may be a simple, indexed, or nested property reference expression. If not specified, the bean identified by `name` is given a new reference identified by `id`.

scope

false

true

`java.lang.String`

Specifies the variable scope searched to retrieve the bean specified by `name`. If not specified, the default rules applied by `PageContext.findAttribute()` are applied.

toScope

false

true

`java.lang.String`

Specifies the variable scope into which the newly defined bean will be created. If not specified, the bean will be created in `page` scope.

type

false

true

`java.lang.String`

Specifies the fully qualified class name of the value to be exposed as the `id` attribute.

value

false

true

`java.lang.String`

The `java.lang.String` value to which the exposed bean should be set. This attribute is required unless you specify the `name` attribute or nested body content.

|-------------------------|
| **Variables**           |
| *No Variables Defined.* |

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
<td align="left"> <a href="tld-summary.html.md"><strong>Library</strong></a> </td>
<td align="left">  Tag  </td>
<td align="left"> <a href="../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"> <a href="../index.html.md"><strong>FRAMES</strong></a>   <a href="define.html"><strong>NO FRAMES</strong></a> 
<a href="../alltags-noframe.html.md"><strong>All Tags</strong></a></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

*Output Generated by [Tag Library Documentation Generator](http://taglibrarydoc.dev.java.net/). Java, JSP, and JavaServer Pages are trademarks or registered trademarks of Sun Microsystems, Inc. in the US and other countries. Copyright 2002-4 Sun Microsystems, Inc. 4150 Network Circle Santa Clara, CA 95054, U.S.A. All Rights Reserved.*
