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
<td align="left"><a href="class-use/ExceptionHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/DynaActionFormClass.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ForwardingActionForward.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ExceptionHandler.html"><strong>FRAMES</strong></a>    <a href="ExceptionHandler.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.action
 Class ExceptionHandler
------------------------

    java.lang.Object
      org.apache.struts.action.ExceptionHandler

------------------------------------------------------------------------

    public class ExceptionHandler

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

An **ExceptionHandler** is configured in the Struts configuration file to handle a specific type of exception thrown by an `Action.execute` method.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` INCLUDE_PATH`
           The name of a configuration property which can be set to specify an alternative path which should be used when the HttpServletResponse has already been committed.

`static String`

` SILENT_IF_COMMITTED`
           The name of a configuration property which indicates that Struts should do nothing if the response has already been committed.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` ExceptionHandler()`   
                          |

  <span id="method_summary"></span>

**Method Summary**

`protected  String`

` determineIncludePath(ExceptionConfig config, ActionForward actionForward)`
           Return a path to which an include should be attempted in the case when the response was committed before the `ExceptionHandler` was invoked.

` ActionForward`

` execute(Exception ex, ExceptionConfig ae, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response)`
            Handle the Exception.

`protected  void`

` handleCommittedResponse(Exception ex, ExceptionConfig config, ActionMapping mapping, ActionForm formInstance, HttpServletRequest request, HttpServletResponse response, ActionForward actionForward)`
           Attempt to give good information when the response has already been committed when the exception was thrown.

`protected  void`

` logException(Exception e)`
           Logs the `Exception` using commons-logging.

`protected  void`

` storeException(HttpServletRequest request, String property, ActionMessage error, ActionForward forward, String scope)`
           Default implementation for handling an `ActionMessage` generated from an `Exception` during `Action` delegation.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="INCLUDE_PATH"></span>

### INCLUDE\_PATH

    public static final String INCLUDE_PATH

The name of a configuration property which can be set to specify an alternative path which should be used when the HttpServletResponse has already been committed.

To use this, in your `struts-config.xml` specify the exception handler like this:

       <exception
           key="GlobalExceptionHandler.default"
           type="java.lang.Exception"
           path="/ErrorPage.jsp">
           <set-property key="INCLUDE_PATH" value="/error.jsp" />
       </exception>
      

You would want to use this when your normal ExceptionHandler path is a Tiles definition or otherwise unsuitable for use in an `include` context. If you do not use this, and you do not specify "SILENT\_IF\_COMMITTED" then the ExceptionHandler will attempt to forward to the same path which would be used in normal circumstances, specified using the "path" attribute in the \<exception\> element.

**Since:**  
Struts 1.3

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.action.ExceptionHandler.INCLUDE_PATH)

------------------------------------------------------------------------

<span id="SILENT_IF_COMMITTED"></span>

### SILENT\_IF\_COMMITTED

    public static final String SILENT_IF_COMMITTED

The name of a configuration property which indicates that Struts should do nothing if the response has already been committed. This suppresses the default behavior, which is to use an "include" rather than a "forward" in this case in hopes of providing some meaningful information to the browser.

To use this, in your `struts-config.xml` specify the exception handler like this:

       <exception
           key="GlobalExceptionHandler.default"
           type="java.lang.Exception"
           path="/ErrorPage.jsp">
           <set-property key="SILENT_IF_COMMITTED" value="true" />
       </exception>
      

To be effective, this value must be defined to the literal String "true". If it is not defined or defined to any other value, the default behavior will be used.

You only need to use this if you do not want error information displayed in the browser when Struts intercepts an exception after the response has been committed.

**Since:**  
Struts 1.3

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.action.ExceptionHandler.SILENT_IF_COMMITTED)

<span id="constructor_detail"></span>

**Constructor Detail**

### ExceptionHandler

    public ExceptionHandler()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(Exception ex,
                                 ExceptionConfig ae,
                                 ActionMapping mapping,
                                 ActionForm formInstance,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws ServletException

Handle the Exception. Return the ActionForward instance (if any) returned by the called ExceptionHandler.

**Parameters:**  
`ex` - The exception to handle

`ae` - The ExceptionConfig corresponding to the exception

`mapping` - The ActionMapping we are processing

`formInstance` - The ActionForm we are processing

`request` - The servlet request we are processing

`response` - The servlet response we are creating

**Returns:**  
The `ActionForward` instance (if any) returned by the called `ExceptionHandler`.

**Throws:**  
`ServletException` - if a servlet exception occurs

**Since:**  
Struts 1.1

------------------------------------------------------------------------

### handleCommittedResponse

    protected void handleCommittedResponse(Exception ex,
                                           ExceptionConfig config,
                                           ActionMapping mapping,
                                           ActionForm formInstance,
                                           HttpServletRequest request,
                                           HttpServletResponse response,
                                           ActionForward actionForward)

Attempt to give good information when the response has already been committed when the exception was thrown. This happens often when Tiles is used. Base implementation will see if the INCLUDE\_PATH property has been set, or if not, it will attempt to use the same path to which control would have been forwarded.

**Parameters:**  
`ex` - The exception to handle

`config` - The ExceptionConfig we are processing

`mapping` - The ActionMapping we are processing

`formInstance` - The ActionForm we are processing

`request` - The servlet request we are processing

`response` - The servlet response we are creating

`actionForward` - The ActionForward we are processing

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### determineIncludePath

    protected String determineIncludePath(ExceptionConfig config,
                                          ActionForward actionForward)

Return a path to which an include should be attempted in the case when the response was committed before the `ExceptionHandler` was invoked.

If the `ExceptionConfig` has the property `INCLUDE_PATH` defined, then the value of that property will be returned. Otherwise, the ActionForward path is returned.

**Parameters:**  
`config` - Configuration element

`actionForward` - Forward to use on error

**Returns:**  
Path of resource to include

**Since:**  
Struts 1.3

------------------------------------------------------------------------

### logException

    protected void logException(Exception e)

Logs the `Exception` using commons-logging.

**Parameters:**  
`e` - The Exception to LOG.

**Since:**  
Struts 1.2

------------------------------------------------------------------------

### storeException

    protected void storeException(HttpServletRequest request,
                                  String property,
                                  ActionMessage error,
                                  ActionForward forward,
                                  String scope)

Default implementation for handling an `ActionMessage` generated from an `Exception` during `Action` delegation. The default implementation is to set an attribute of the request or session, as defined by the scope provided (the scope from the exception mapping). An `ActionMessages` instance is created, the error is added to the collection and the collection is set under the `Globals.ERROR_KEY`.

**Parameters:**  
`request` - The request we are handling

`property` - The property name to use for this error

`error` - The error generated from the exception mapping

`forward` - The forward generated from the input path (from the form or exception mapping)

`scope` - The scope of the exception mapping.

**Since:**  
Struts 1.2

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
<td align="left"><a href="class-use/ExceptionHandler.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/DynaActionFormClass.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/ForwardingActionForward.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/ExceptionHandler.html"><strong>FRAMES</strong></a>    <a href="ExceptionHandler.html"><strong>NO FRAMES</strong></a>    
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
