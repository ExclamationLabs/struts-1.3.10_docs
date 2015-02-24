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
<td align="left"><a href="class-use/ScriptAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/scripting/RequestToVariableFilter.html.md" title="class in org.apache.struts.scripting"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/scripting/StrutsInfo.html" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/ScriptAction.html"><strong>FRAMES</strong></a>    <a href="ScriptAction.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.scripting
 Class ScriptAction
---------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.scripting.ScriptAction

------------------------------------------------------------------------

    public class ScriptAction

extends [Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")

This Action uses scripts to perform its action. The scripting framework is Apache's Bean Scripting Framework which allows the scripts to be written many of the popular scripting languages including JavaScript, Perl, Python, and even VBA.
 To determine what script will be executed, the "parameter" attribute of the action mapping should contain the name of the script relative to the web application root directory (i.e. http://server/app).
 Before the script completes, the next ActionForward needs to be specified. This can be done one of two ways:

1.  Set `struts.forwardName` to the name of the forward
2.  Set `struts.forward` to the actual ActionForward object

A number of pre-defined variables are available to the script:

-   `request` - The HTTP request
-   `response` - The HTTP response
-   `session` - The session
-   `application` - The servlet context
-   `struts` - A grouping of all Struts-related objects
-   `log` - A logging instance

You can add your own variables by creating a BSFManagerFilter and configuring it in struts-scripting.properties:

-   `struts-scripting.filters.FILTER_NAME.class=FILTER_CLASS` - The class implementing BSFManagerFilter where FILTER\_NAME is the name you are calling the filter.
-   `struts-scripting.filters.FILTER_NAME.PROPERTY_NAME=PROPERTY_VALUE` - A property to be used by the filter.

 To use other scripting engines other than BeanShell, create a file called `struts-scripting.properties` and add two properties for each engine:

-   `struts-scripting.engine.ENGINE_NAME.class` - The class of the BSF engine where ENGINE\_NAME is the name you are calling the engine.
-   `struts-scripting.engine.ENGINE_NAME.extensions` - A comma-delimited list of file extensions that will be used to identify the engine to use to execute the script.

This code was originally based off code from JPublish, but has since been almost completely rewritten.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static String`

` ENGINE_BASE`
           The base property for alternate BSF engines.

`protected static String`

` FILTERS_BASE`
           The base property for classes that put new variables in the context.

`protected static Log`

`LOG`
           The logging instance.

`protected static String`

` PROPS_PATH`
           The default path to the properties file.

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                               |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ScriptAction()`       
                          |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Executes the script.

` Locale`

` getLocale(HttpServletRequest req)`
           Gets the locale.

` boolean`

` isCancelled(HttpServletRequest req)`
           Checks to see if the request is cancelled.

` boolean`

` isTokenValid(HttpServletRequest req)`
           Checks to see if the token is valid.

`protected static BSFManagerFilter[]`

` loadFilters(Properties props)`
           Loads and initializes the filters.

`protected  org.apache.struts.scripting.ScriptAction.Script`

` loadScript(String name, ServletContext context)`
           Loads the script from cache if possible.

`protected  String`

` parseScriptName(String url, org.apache.bsf.BSFManager manager)`
           Parses the script name and puts any url parameters in the context.

` void`

` resetToken(HttpServletRequest req)`
           Resets the token.

` void`

` saveErrors(HttpServletRequest req, ActionErrors errs)`
           **Deprecated.** *Use saveErrors(HttpServletRequest, ActionMessages) instead. This will be removed after Struts 1.2.*

` void`

` saveMessages(HttpServletRequest req, ActionMessages mes)`
           Saves the messages to the request.

` void`

` saveToken(HttpServletRequest req)`
           Saves a token.

`protected static String[]`

` split(String line, String delimiter)`
           Splits a line with the given delimiter.

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")**                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addErrors,  addMessages,  execute,  generateToken,  getErrors,  getMessages,  getResources,  getResources, getServlet,  isTokenValid,  saveErrors,  saveErrors,  saveMessages,  setLocale,  setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="LOG"></span>

### LOG

    protected static final Log LOG

The logging instance.

------------------------------------------------------------------------

<span id="PROPS_PATH"></span>

### PROPS\_PATH

    protected static final String PROPS_PATH

The default path to the properties file.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.scripting.ScriptAction.PROPS_PATH)

------------------------------------------------------------------------

<span id="ENGINE_BASE"></span>

### ENGINE\_BASE

    protected static final String ENGINE_BASE

The base property for alternate BSF engines.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.scripting.ScriptAction.ENGINE_BASE)

------------------------------------------------------------------------

<span id="FILTERS_BASE"></span>

### FILTERS\_BASE

    protected static final String FILTERS_BASE

The base property for classes that put new variables in the context.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.scripting.ScriptAction.FILTERS_BASE)

<span id="constructor_detail"></span>

**Constructor Detail**

### ScriptAction

    public ScriptAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Executes the script.

**Overrides:**  
` execute` in class `Action`

<!-- -->

**Parameters:**  
`mapping` - The action mapping

`form` - The action form

`request` - The request object

`response` - The response object

**Returns:**  
The action forward

**Throws:**  
`Exception` - If something goes wrong

------------------------------------------------------------------------

### parseScriptName

    protected String parseScriptName(String url,
                                     org.apache.bsf.BSFManager manager)
                              throws Exception

Parses the script name and puts any url parameters in the context.

**Parameters:**  
`url` - The script url consisting of a path and optional parameters

`manager` - The BSF manager to declare new parameters in

**Returns:**  
The name of the script to execute

**Throws:**  
`Exception` - If something goes wrong

------------------------------------------------------------------------

### loadScript

    protected org.apache.struts.scripting.ScriptAction.Script loadScript(String name,
                                                                         ServletContext context)

Loads the script from cache if possible. Reloads if the script has been recently modified.

**Parameters:**  
`name` - The name of the script

`context` - The servlet context

**Returns:**  
The script object

------------------------------------------------------------------------

### loadFilters

    protected static BSFManagerFilter[] loadFilters(Properties props)

Loads and initializes the filters.

**Parameters:**  
`props` - The properties defining the filters

**Returns:**  
An array of the loaded filters

------------------------------------------------------------------------

### split

    protected static String[] split(String line,
                                    String delimiter)

Splits a line with the given delimiter.

**Parameters:**  
`line` - The line to split

`delimiter` - The string to split with

**Returns:**  
An array of substrings

------------------------------------------------------------------------

### saveToken

    public void saveToken(HttpServletRequest req)

Saves a token.

**Overrides:**  
` saveToken` in class `Action`

<!-- -->

**Parameters:**  
`req` - The request object

------------------------------------------------------------------------

### isCancelled

    public boolean isCancelled(HttpServletRequest req)

Checks to see if the request is cancelled.

**Overrides:**  
` isCancelled` in class `Action`

<!-- -->

**Parameters:**  
`req` - The request object

**Returns:**  
True if cancelled

------------------------------------------------------------------------

### isTokenValid

    public boolean isTokenValid(HttpServletRequest req)

Checks to see if the token is valid.

**Overrides:**  
` isTokenValid` in class `Action`

<!-- -->

**Parameters:**  
`req` - The request object

**Returns:**  
True if valid

------------------------------------------------------------------------

### resetToken

    public void resetToken(HttpServletRequest req)

Resets the token.

**Overrides:**  
` resetToken` in class `Action`

<!-- -->

**Parameters:**  
`req` - The request object

------------------------------------------------------------------------

### getLocale

    public Locale getLocale(HttpServletRequest req)

Gets the locale.

**Overrides:**  
` getLocale` in class `Action`

<!-- -->

**Parameters:**  
`req` - The request object

**Returns:**  
The locale value

------------------------------------------------------------------------

### saveMessages

    public void saveMessages(HttpServletRequest req,
                             ActionMessages mes)

Saves the messages to the request.

**Overrides:**  
` saveMessages` in class `Action`

<!-- -->

**Parameters:**  
`req` - The request object

`mes` - The action messages

------------------------------------------------------------------------

### saveErrors

    public void saveErrors(HttpServletRequest req,
                           ActionErrors errs)

**Deprecated.** *Use saveErrors(HttpServletRequest, ActionMessages) instead. This will be removed after Struts 1.2.*

Saves the errors to the request.

**Parameters:**  
`req` - The request object

`errs` - The action errors

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
<td align="left"><a href="class-use/ScriptAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/scripting/RequestToVariableFilter.html.md" title="class in org.apache.struts.scripting"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/scripting/StrutsInfo.html" title="class in org.apache.struts.scripting"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/scripting/ScriptAction.html"><strong>FRAMES</strong></a>    <a href="ScriptAction.html"><strong>NO FRAMES</strong></a>    
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
